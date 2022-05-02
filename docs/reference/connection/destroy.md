---
sidebar_position: 10
---

# destroy

:::caution
If you have registered any intervals you should override the destroy function
and clear them here.
:::

Destroys the connection.

- Send a `close` frame
- Destroy the socket
- Deletes the connection from the server

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
