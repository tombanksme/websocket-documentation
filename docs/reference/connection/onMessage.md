---
sidebar_position: 5
---

# onMessage

Handle incoming message.

```typescript title="/src/CustomConnection.ts"
import { Connection, Message } from "@tombanksme/websockets";

class CustomConnection extends Connection {
    /**
     * Handle incoming message.
     *
     * @param message
     */
    onMessage(message: Message) {
        // Application logic here.
    }
}
```
