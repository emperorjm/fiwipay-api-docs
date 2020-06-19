---
tags: [Error Handling]
---

# Error Handling

In order to handle API errors gracefully, exceptions are thrown when errors occur which will return an error response with the relevant error code in the response header and message, for example:

```json
{
  "error": {
    "message": "The given data was invalid"
  }
}
```

The status codes that may be returned from the API are detailed below:

| Status Code | Description                                                                                 |
| ----------- | ------------------------------------------------------------------------------------------- |
| 200         | **OK** - The request has succeeded                                                          |
| 400         | **Bad Request** - The server could not understand the request due to invalid syntax or data |
| 401         | **Unauthorized** - Client is not authenticated or authentication failed                     |
| 404         | **Not Found** - The resource does not exist                                                 |
| 422         | **Unprocessable Entity** - The request was not well-formed and validation failed                |
| 500         | **Server Error** - An error has occurred on fiwiPay's backend                               |
