---
sidebar_position: 2
---

# onFrame

:::danger
We do not reccommend overriding this hook, as it is responsible for calling other hooks
and assembling messages from frame fragments.
:::

Handle all incoming frames.

```typescript title="/src/CustomConnection.ts"
import { Connection, FrameInterface } from "@tombanksme/websockets";

class CustomConnection extends Connection {
	/**
	 * Handle incoming frame.
	 *
	 * @param frame
	 */
	onFrame(frame: FrameInterface) {
		switch (frame.getOp()) {
			case Opcode.PING:
				this.onPing(frame);
				break;
			case Opcode.PONG:
				this.onPong(frame);
				break;
		}
	}
}
```
