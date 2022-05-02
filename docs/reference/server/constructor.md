---
sidebar_position: 1
---

# constructor

```typescript title='/src/index.ts'
import { Server } from "server";
import { createServer } from "http";

const http = createServer();
const server = new Server(http);
```
