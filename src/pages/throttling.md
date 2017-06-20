API requests are limited to the amount specified in the returned `X-RateLimit-Limit` header (per 10 seconds). Exceeding that limit will cause Harvest to return an `HTTP 429` response. Check the `X-RateLimit-Limit` and `X-RateLimit-Remaining` headers to see how many more requests you are allowed until throttling kicks in.

    Status: 200 OK
    X-RateLimit-Limit: 50
    X-RateLimit-Remaining: 49
