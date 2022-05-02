---
sidebar_position: 7
---

# ping

Send a `ping` frame.

```typescript title="/src/CustomConnection.ts"
import { Duplex } from "stream";
import { Server, Connection } from "@tombanksme/websockets";

class CustomConnection extends Connection {
    constructor(server: Server, sock: Duplex) {
        super(server, sock);

        setInterval(() => {
            this.ping(); // Send 'ping' frame.
        }, 5000);
    }
}
```
