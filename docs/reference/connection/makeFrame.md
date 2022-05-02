---
sidebar_position: 11
---

# makeFrame

```typescript title='/src/CustomConnection.ts'
import CustomFrame from "./CustomFrame";

import {
	Connection,
	FrameParameters,
	FrameInterface,
} from "@tombanksme/websockets";

class CustomConnection extends Connection {
	/**
	 * Make a frame.
	 *
	 * @param params
	 */
	makeFrame(params: FrameParameters): FrameInterface {
		return new CustomFrame(params);
	}
}
```
