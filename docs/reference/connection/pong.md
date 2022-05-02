---
sidebar_position: 8
---

# pong

Send a `pong` frame.

```typescript title="/src/CustomConnection.ts"
import { Connection } from "@tombanksme/websockets";

class CustomConnection extends Connection {
    onPing(frame: FrameInterface) {
        this.pong(); // Send 'pong' frame.
    }
}
```
