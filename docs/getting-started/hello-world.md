---
sidebar_position: 2
---

# Hello World

To begin we will create a simple server & connection which will send PING frames
to the client every 10 seconds.

### Writing the server

The server class is responsible for upgrading & managing WebSocket connections. For this
demonstration we won't need to customise this class much.

We will need to override the `makeConnection` method to return an instance of our
`HeartbeatConnection` which we will create in the next section.

```typescript title="/src/server.ts"
import { Server } from "@tombanksme/websockets";
import HeartbeatConnection from "./HeartbeatConnection";

export class HeartbeatServer extends Server {
    /**
     * Make a new connection.
     *
     * @param req
     * @param sock
     * @param head
     */
    makeConnection(req, sock, head) {
        return new HeartbeatConnection(this, sock);
    }
}

export default HeartbeatServer;
```

### Writing the connection

The connection class handles the majority of the protocol logic. We can define custom behavour using a hook.

Here we use the `onPong` hook to detect that we recieved a pong frame; increment the
heartbeat count; and print the current count to the console.

```typescript title="/src/connection.ts"
import { Duplex } from "duplex";
import { Connection, ServerInterface } from "@tombanksme/websockets";

export class HeartbeatConnection extends Connection {
    protected heartbeat = 0;

    protected heartbeatCount = 0;

    constructor(protected svr: ServerInterface, protected sock: Duplex) {
        super(svr, sock);

        this.heartbeat = setTimeout(() => {
            this.ping();
        }, 10000);
    }

    /**
     * Handle pong frame.
     *
     * @param frame The incoming frame
     */
    onPong(frame) {
        this.heartbeatCount++;

        console.log(`Heartbeat count: ${this.heartbeatCount}`);
    }
}

export default HeartbeatConnection;
```

### Starting the application

Finally we can import our `HeartbeatServer` and start it; listening for connections on port 8080.

```typescript title="/src/index.ts"
import Http from "http";
import HeartbeatServer from "./server";

const http = Http.createServer();

const server = new HeartbeatServer(http);

http.listen(8080);
```

### Congratulations!

You've successfully created your first WebSocket application. You can find information
about creating more complicated applications in the documentation.
