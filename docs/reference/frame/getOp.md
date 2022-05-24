---
sidebar_position: 3
---

# getOp

Gets the frame's opcode.

```typescript
import { Frame, Opcode } from "@tombanksme/websockets";

const frame = new Frame({
    /* ... */
});

if (frame.getOp() == Opcode.BIN) {
    console.log("This is a binary frame");
}
```
