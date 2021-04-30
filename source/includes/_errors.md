# Errors

> Handling Errors

```shell
# Select a client library to see examples of handling different kinds of errors.
```

Recursion.Space API uses conventional HTTP response codes to indicate the sucess or failure of an API call. In general: Codes in the <code>2xx</code> range indicate success. Codes in the <code>4xx</code> range indicate an error that failed given the information provided. Codes in the <code>5xx</code> range indicate an error with Recursion.Space servers (these are rare).

| Error Code | Meaning                                                         |
| ---------- | --------------------------------------------------------------- |
| 400        | Bad Request -- Your request is invalid.                         |
| 403        | Authentication -- You do not have permission to view resource.  |
| 405        | Bad Method -- Method used (GET, POST, DELETE, PUT) not allowed. |
| 418        | I'm a teapot.                                                   |
