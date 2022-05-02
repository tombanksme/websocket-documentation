---
sidebar_position: 5
---

# onMessage

```typescript title="/src/CustomConnection.ts"
import { Connection } from "@tombanksme/websocket";

class CustomConnection extends Connection {
	/**
	 * Handle incoming message.
	 *
	 * @param message
	 */
	onMessage(message: Message) {
		// Application logic here.
	}
}
```
