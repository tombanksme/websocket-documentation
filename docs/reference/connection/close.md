---
sidebar_position: 9
---

# close

:::caution
You should use [destory](/docs/reference/connection/destroy) instead of calling the close function.
:::

Send a `close` frame.

```typescript title="/src/CustomConnection.ts"
import { Duplex } from "stream";
import { Server, Connection } from "@tombanksme/websockets";

class CustomConnection extends Connection {
	constructor(server: Server, sock: Duplex) {
		super(server, sock);

		this.close(); // Sends 'close' frame.
	}
}
```
