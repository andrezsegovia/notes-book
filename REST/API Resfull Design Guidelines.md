# API Restful Design Guidelines	

## Endpoint URLs and HTTP status codes

The following list contains the generally accepted rules that a well-defined API should follow. 

- When a resource is created, the API should return a 201 Created status code, followed by a location header that specifies the URL where the newly resource can be accessed.
- Operation that creates resources may be implemented to gracefully reject creation of resources, which unique identifiers already use; the operation response should indicate a non-successful invocation with an appropriate status code 409 Conflict, or a more general 400 BAD REQUEST.
- The Update operation resembles the create operation; however, it always expects a resource identifier as a parameter, if a resource with this identifier exists -it gets updated with a new state provided in the body of the HTTP PUT request. The 200 OK status code indicates successful invocation. Also, the implementation may decide to reject handling of non-existent resources with the 404 Not Found status code or create a new resource with the passed identifier.
- While successful deletion can be indicated with the 204 No Content status and further a payload, most user agents would expect the 2xx HTTP status to be followed by a body. 
- As a general rule, 5xx should not indicate application state errors but more server errors, such as application server or database failures. 
- It is best practice that update and create operation should return as a payload to the entire state of the resource. This may save the user-agent an addition GET request if the needed to check the new state.

## Extensibility and versioning

When we need to create the next version of our Restful API, may we want to continue giving the service to whose are using the first version and indicate to them the change but without affected their implementations. 

What we should do is redirect all the first version endpoint to the a new endpoint that uses the first version and expose the new version at a different endpoint.

![1566613088794](/home/me/.config/Typora/typora-user-images/1566613088794.png)

