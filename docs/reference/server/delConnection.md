---
sidebar_position: 3
---

# delConnection

Deletes an active [Connection](/docs/reference/connection/constructor). This method does not destroy the connection; it only removes the Connection object from the server's active connections array.

```typescript title="/src/CustomConnection.ts"
const server = new HeartbeatServer(/* ... */);

// Remove the first connection.

if (server.getConnections().length > 0) {
    server.delConnection(server.getConnections()[0]);
}
```
