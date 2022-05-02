---
sidebar_position: 6
---

# onClose

Handle incoming `close` frame.

```typescript title="/src/CustomConnection.ts"
import { Connection, FrameInterface } from "@tombanksme/websockets";

class CustomConnection extends Connection {
	/**
	 * Handle close frame.
	 *
	 * @param frame
	 */
	onClose(frame: FrameInterface) {
		if (!this.sock.destroyed) {
			this.sock.destroy();
		}

		this.server.delConection(this);
	}
}
```
