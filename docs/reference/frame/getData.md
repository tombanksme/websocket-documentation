---
sidebar_position: 5
---

# getData

Gets the data from the frame.

```typescript
import { Frame, Opcode } from "@tombanksme/websockets";

const frame = new Frame({
    /* ... */
});

if (frame.isFinal() && frame.getOp() == Opcode.TXT) {
    console.log(frame.getData.toString());
}
```
