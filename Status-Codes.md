## Most common HTTP status codes

- HTTP status codes are three-digit numbers included in the server’s response that indicate the result of a client’s request. Some of the most common HTTP status codes include:

1. **200 OK:** The request was successful, and the response includes the requested data.

2. **201 Created:** The request was successful, and the server has created a new resource with the provided data.

3. **204 No Content:** The request was successful, but there is no additional data to send in the response. This code is often used in response to DELETE requests.

4. **400 Bad Request:** The server cannot understand the request due to a client error, malformed syntax, or invalid parameters.

5. **401 Unauthorized:** The client lacks valid credentials to access the requested data or perform the desired action.

6. **403 Forbidden:** The client does not have permission to access the requested resource, even with valid authentication credentials.

7. **404 Not Found:** The server cannot find the requested resource or endpoint.

8. **405 Method Not Allowed:** The requested HTTP method is not supported for the specified resource.

9. **500 Internal Server Error:** The server encountered an unexpected issue.

10. **502 Bad Gateway:** The server acting as a gateway or proxy received an invalid response from an upstream server.

11. **503 Service Unavailable:** The server is not ready to handle the request, often due to overload or maintenance.

12. **504 Gateway Timeout:** The server acting as a gateway or proxy did not receive a timely response from the upstream server.

## The four primary HTTP request methods in REST:

1. **GET:** Requests a resource from the server. (Note that GET cannot modify server resources, as it is a read-only method.)
2. **POST:** Creates a new resource on the server.
3. **PUT:** Updates an existing resource on the server.
4. **DELETE:** Removes a resource from the server.Additionally, two less common HTTP requests you should also know are:
5. **HEAD:** Requests meta-information about a resource. This request is similar to GET, but the response does not include a response body.
6. **OPTIONS:** Retrieves a list of possible methods for a resource.
- **CRUD** stands for “Create, Read, Update, Delete
  - Create = POST
  - Read = GET
  - Update = PUT
  - Delete = DELETE
