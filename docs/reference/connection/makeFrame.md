---
sidebar_position: 12
---

# makeFrame

This factory method specifies which [Frame](/docs/reference/frame/constructor) the Connection will use.

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
