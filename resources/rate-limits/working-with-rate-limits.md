# Working with Rate Limits

## Overview

Hexsafe monitors API call traffic to maintain a stable and secure platform and tp prevent system overload. API rate limits prevent a single client from overburdening the system. HTTP 429 responses denote temporary rate limit exceedance. Persistent rate limiting during test or production operations should be reported to Hexsafe Support.

API rate limits are set at the API endpoint level. If you regularly receive HTTP 429 responses, do your best to limit the rate of requests, spread them out across minute intervals, or spread them out across multiple API users.\


API rate limits are assigned per user. If you regularly encounter HTTP 429 responses, try to distribute requests evenly across minute intervals or multiple API users. Common rate limit error triggers include unmonitored 429 errors, retrying failed API calls without identifying error type, excessive parallel processes for batch operations, monitoring transactions via polling rather than webhooks, and frequent checks of gas or token prices.

## Recommended Practices

**Monitor rate limit errors** - Regularly receiving 429 errors implies potential issues. Reflect on how a solution architecture modification could decrease the volume of your API calls.

**Retry API calls reasonably** - If periodic API calls are part of your process, avoid unnecessary retries/persistence by relying on the next scheduled check. When retries are essential, consider implementing an exponential backoff strategy.

**Incorporate Caching** - Most all elements do not require constant verification with each transaction. Consider implementing caching for data points that require only periodic updates.

\
\


\
\
