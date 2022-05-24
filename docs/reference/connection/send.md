---
sidebar_position: 10
---

# send

Sends a message to the connection. If the parameter is a buffer, a binary message will be sent. If the parameter is a string, a text message will be sent.

```typescript title="/src/CustomConnection.ts"
import { Connection, Message } from "@tombanksme/websockets";

class CustomConnection extends Connection {
    onMessage(message: Message) {
        this.send("Hello World");

        // or

        this.send(Buffer.alloc(4));
    }
}
```
