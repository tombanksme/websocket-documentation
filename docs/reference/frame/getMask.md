---
sidebar_position: 6
---

# getMask

Gets the masking key from the frame.

```typescript
import { Frame } from "@tombanksme/websockets";

const frame = new Frame({
    /* ... */
});

if (frame.isMasked() && frame.getMask()) {
    // Unmask the frame content.
}
```
