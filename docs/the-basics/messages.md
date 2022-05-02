---
sidebar_position: 3
---

# Messages

The default connection class comes with an onMessage hook, which you can use to recieve
text and binary messages from your client.

```typescript title="/src/MessageConnection.ts"
import { Connection, Message, MessageType } from "@tombanksme/websockets";

class MessageConnection extends Connection {
	/**
	 * Handle an incoming message.
	 *
	 * @param message The incoming message.
	 */
	onMessage(message: Message) {
		if (message.type == MessageType.TXT) {
			console.log(message.data.toString());
		}
	}
}
```
