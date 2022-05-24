---
sidebar_position: 4
---

# isMasked

Checks if the frame is marked as masked.

```typescript
import { Frame } from "@tombanksme/websockets";

const frame = new Frame({
    /* ... */
});

if (frame.isMasked()) {
    console.log("This frame is masked.");
}
```
