---
sidebar_position: 2
---

# toFragments

Build frames from a message.

```typescript
import { Buffer } from "buffer";
import { Message, MessageType } from "@tombanksme/websocket";

const message = new Message(MessageType.TXT, Buffer.from("Hello World"));

const frames = message.toFragments(); // [Frame, Frame, ...];
```
