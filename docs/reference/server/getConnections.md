---
sidebar_position: 1
---

# getConnections

Gets all active [Connections](/docs/reference/connection/constructor).

```typescript title="/src/CustomConnection.ts"
const server = new HeartbeatServer(/* ... */);

server.getConnections(); // [Connection, Connection, Connection];
```
