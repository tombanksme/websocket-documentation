---
sidebar_position: 3
---

# Messages

The message class is responsible for fragmentation of string and binary messages.

### Recieving Messages

The default connection class comes with an [onMessage](/docs/the-basics/hooks) hook, which you can use to recieve
text and binary messages from your client.

```typescript title="/src/MessageConnection.ts"
import { Connection, Message, MessageType } from "@tombanksme/websockets";

class MessageConnection extends Connection {
    /**
     * Handle an incoming message.
     *
     * @param message The incoming message.
     */
    onMessage(message: Message) {
        if (message.type == MessageType.TXT) {
            console.log(message.data.toString());
        }
    }
}
```

### Sending Messages

You can send a message to a connection using the [send](/docs/reference/connection/send) method. The message type depends on the parameter given to the send method; a Buffer sends a binary message; a string sends a text message.

```typescript title="/src/MessageConnection.ts"
import { Connection, Message, MessageType } from "@tombanksme/websockets";

class MessageConnection extends Connection {
    /**
     * Handle an incoming message.
     *
     * @param message The incoming message.
     */
    onMessage(message: Message) {
        // Will send text message

        this.send("Hello World");

        // Will send binary message

        this.send(Buffer.alloc(4));
    }
}
```
