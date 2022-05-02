---
sidebar_position: 4
---

# makeConnection

```typescript title='/src/CustomServer.ts'
import CustomConnection from "./CustomConnection";

import { Duplex } from "stream";
import { Server, ConnectionInterface } from "@tombanksme/websockets";

class CustomServer extends Server {
	/**
	 * Make a connection.
	 *
	 * @param sock The connection socket
	 */
	makeConnection(sock: Duplex): ConnectionInterface {
		return new CustomConnection(this, sock);
	}
}
```
