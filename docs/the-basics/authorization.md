---
sidebar_position: 2
---

# Authorization

You may want to limit connections to your WebSocket server to a specific group of people. To do this override the `authorizeUpgrade` function and return `true` or `false`.

```typescript title="/src/AuthorizationServer.ts"
import { IncomingMessage } from "http";
import { Server } from "@tombanksme/websocket";

class AuthorizationServer extends Server {
	/**
	 * Authorize an upgrade.
	 *
	 * @param req The incoming HTTP request
	 */
	protected authorizeUpgrade(req: IncomingMessage) {
		if (req.headers["Authorization"]) {
			return true;
		}

		return false;
	}
}
```
