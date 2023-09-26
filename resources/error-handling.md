# Error Handling

**400: Bad Request**\
\
This status code indicates that the server could not understand the request due to invalid syntax. This could be due to malformed JSON, missing parameters, or invalid values. It's a client-side error, it indicates that the client needs to adjust the request before attempting to resend it.

Example:

```json
{
    "status": 400,
    "message": "The 'email' field is required."
}
```

**401: Unauthorized**

This error code is returned when the client tries to access a resource that requires authentication, but it fails to provide it. This status code informs the client that it needs to authenticate with the server to gain access to the resource.

Example:

```json
{
    "status": 401,
    "message": "Missing or invalid authentication token."
}
```

**403: Forbidden**

Unlike 401, the request is valid, and the client is authenticated, but the client lacks the necessary permissions to access the resource. This can result from insufficient privileges or specific system rules.

Example:

```json
{
    "status": 403,
    "message": "You do not have permission to delete this data."
}
```

**404: Not Found**

This status code is returned when the client tries to access a resource that does not exist on the server. This could be because of an incorrect URL or if the resource has been deleted.

Example:

```json
{
    "status": 404,
    "message": "Data with ID '123' not found."
}
```

**405: Method Not Allowed**

This status code indicates that the HTTP method used is not supported/compatible for the requested resource. For instance, trying to DELETE a read-only resource would result in a 405.

Example:

```json
{
    "status": 405,
    "message": "HTTP method 'POST' not allowed. Only 'GET' is supported."
}
```

**409: Conflict**

This response is returned when a request cannot be completed due to a conflict with the current state of the resource. This might occur when attempting to upload a file with the same name as an existing file, for example.

Example:

```json
{
    "status": 409,
    "message": "A user with email 'example@example.com' already exists."
}
```

**429: Too Many Requests**

This status code is returned when the client has sent too many requests in a given amount of time ("rate limiting").

Example:

```json
{
    "status": 429,
    "message": "Rate limit exceeded."
}
```

**500: Internal Server Error**

This is a generic error message when an unexpected condition was encountered and no more specific message is suitable. It indicates a problem on the server's side, and the client might not have done anything wrong.

Example:

```json
{
    "status": 500,
    "message": "Internal server error. Please try again later."
}
```

**502: Bad Gateway**

This error response means that the server, while working as a gateway to get a response needed to handle the request, got an invalid response.

Example:

```json
{
    "status": 502,
    "message": "Bad Gateway. The upstream server sent an invalid response."
}
```

**503: Service Unavailable**

The server is currently unable to handle the request due to a temporary overload or scheduled maintenance, which will likely be alleviated after some delay.

Example:

```json
{
    "status": 503,
    "message": "Service Unavailable. Please try again later."
}
```

**504: Gateway Timeout**&#x20;

This error response is given when the server is acting as a gateway and cannot get a response in time.

Example:

```json
{
    "status": 504,
    "message": "Gateway Timeout. The server, while acting as a gateway, did not receive a timely response from the upstream server it accessed in attempting to complete the request."
}
```
