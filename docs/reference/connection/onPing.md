---
sidebar_position: 3
---

# onPing

:::caution
When overriding this hook, remember to call the `pong` method. Failiure to do so will mean
that you application is not RFC 6455 compliant.
:::

Handle incoming `ping` frame.

```typescript title='/src/CustomConnection.ts'
import { Connection, FrameInterface } from "@tombanksme/websocket";

class CustomConnection extends Connection {
	/**
	 * Handle ping frame.
	 *
	 * @param frame
	 */
	onPing(frame: FrameInterface) {
		this.pong();
	}
}
```
