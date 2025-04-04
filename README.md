## tollbooth_gin

[Gin](https://github.com/gin-gonic) middleware for rate limiting HTTP requests.

## Five Minutes Tutorial

```
package main

import (
    "github.com/didip/tollbooth/v7"
    "github.com/didip/tollbooth_gin"
    "github.com/gin-gonic/gin"
)

func main() {
    r := gin.New()

    // Create a limiter struct.
    limiter := tollbooth.NewLimiter(1, nil)

    r.GET("/", tollbooth_gin.LimitHandler(limiter), func(c *gin.Context) {
        c.String(200, "Hello, world!")
    })

    r.Run(":12345")
}
```
