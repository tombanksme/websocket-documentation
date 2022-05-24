---
sidebar_position: 2
---

# isFinal

Checks if the frame is marked as final.

```typescript
import { Frame } from "@tombanksme/websockets";

const frame = new Frame({
    /* ... */
});

if (frame.isFinal()) {
    console.log("Last frame in fragmented message");
}
```
