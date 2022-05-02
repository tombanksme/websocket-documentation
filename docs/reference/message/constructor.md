---
sidebar_position: 1
---

# constructor

```typescript
import { Buffer } from "buffer";
import { Message, MessageType } from "@tombanksme/websockets";

const message = new Message(MessageType.TXT, Buffer.from("Hello World"));
```
