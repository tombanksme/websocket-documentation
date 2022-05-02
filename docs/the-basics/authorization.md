---
sidebar_position: 2
---

# Authorization

For some services, you may want to authorize upgrade requests. With this library, this
task is simple.

Simply override the authorizeUpgrade function to your Server class and return true or
false.

```typescript title="/src/AuthorizationServer.ts"
import { IncomingMessage } from "http";
import { Server } from "@tombanksme/websockets";

class AuthorizationServer extends Server {
    /**
     * Authorize an upgrade.
     *
     * @param req The incoming HTTP request
     */
    protected authorizeUpgrade(req: IncomingMessage) {
        if (req.headers["Authorization"] === "Bearer ...") {
            return true;
        }

        return false;
    }
}
```
