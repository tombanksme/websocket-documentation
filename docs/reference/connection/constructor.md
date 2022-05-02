---
sidebar_position: 1
---

# constructor

Construct a new Connection.

```typescript
import { Server, Connection } from "@tombanksme/websockets";

export class HeartbeatServer extends Server {
	/**
	 * Make a new connection.
	 *
	 * @param req
	 * @param sock
	 * @param head
	 */
	makeConnection(req, sock, head) {
		return new Connection(this, sock);
	}
}

export default HeartbeatServer;
```
