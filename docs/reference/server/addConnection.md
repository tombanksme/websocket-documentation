---
sidebar_position: 2
---

# delConnection

Adds an active [Connection](/docs/reference/connection/constructor) to the server.

```typescript title="/src/CustomConnection.ts"
const server = new HeartbeatServer(/* ... */);

server.addConnection(new Connection(/* ... */));
```
