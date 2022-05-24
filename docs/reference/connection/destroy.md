---
sidebar_position: 11
---

# destroy

:::caution
If you have registered any intervals you should override the destroy function
and clear them here.
:::

This method destroys the connection by:

-   Sending a `close` frame
-   Destroys the socket
-   Deletes the connection from the server

```typescript title="/src/CustomConnection.ts"
import { Duplex } from "stream";
import { Server, Connection } from "@tombanksme/websockets";

class CustomConnection extends Connection {
    constructor(server: Server, sock: Duplex) {
        super(server, sock);

        this.destory(); // Sends 'close' frame and destroys socket.
    }
}
```
