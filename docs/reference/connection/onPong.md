---
sidebar_position: 4
---

# onPong

Handle incoming `pong` frame.

```typescript title='/src/CustomConnection.ts'
import { Connection, FrameInterface } from "@tombanksme/websockets";

class CustomConnection extends Connection {
    /**
     * Handle pong frame.
     *
     * @param frame
     */
    onPong(frame: FrameInterface) {
        // ...
    }
}
```
