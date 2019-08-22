# Representational State Transfer (REST)

The key principles around the HTTP and URI standards, sticking to which will make your HTTP application a RESTFul service-enabled application. 

- Everything is a resource
- Each resource is identifiable by a unique identifier (URI)
- Resources are manipulated via standard HTTP methods
- Resources can have multiple representations
- Communicate with resources in a stateless manner

## Principle 1 - Everything is a resource 

Each piece of date available on the Internet has a format that describes it, known as the content type: for example, JPEG images, MPEG videos, HTML, XML, text documents, and binary data are all resources with the following content types: images/jpeg, video/mpeg, text/html, text/xml, and application/octect-stream.

## Principle 2 -  Each resource is identifiable by a unique identifier

The resources on the Internet should be accessible via URIs and should be identified uniquely. Furthermore, the URIs can be in human-readable format.

Human-readable URIs keep data self-descriptive and ease further development against it. This helps you to keep the risk of logical errors in your programs to a minimum.

## Principle 3 - Manipulate resources via standard HTTP methods

The native HTTP protocol; (RFC 2616) defines eight actions, also known as HTTP verbs:

- GET
- POST
- PUT
- DELETE
- HEAD
- OPTIONS
- TRACE
- CONNECT

If you apply the REST principles correctly, the HTTP verbs should be used as shown here:

| HTTP Verb | Action                                                       | HTTP Response status code                                    |
| --------- | ------------------------------------------------------------ | :----------------------------------------------------------- |
| GET       | Retrieves an existing resource                               | `200 OK` it the resource exists, `404 Not Found` if it does not exist, and `500 Internal Server Error` for other errors. |
| PUT       | Update a resource. If the resource does not exist, the server can either decide to create it with the provided identifier or return the appropriate status code. | `200 OK` if successfully updated, `201 Created` if a new resource is created, `404 Not Found` if the resource to be updated does not exists, and `500 Internal Server Error` for other unexpected errors. |
| POST      | Creates a resource with an identifier generated at server side or updates a resource with an existing identifier provided for the client. If the verb is to be used only for creating but not for updating, return the appropriate status code. | `201 CREATE` if a new resource is created, `200 OK` if the resource has been updated successfully, `409 CONFLICT` if the resource already exist and update is not allowed,`404 NOT FOUND` if the resource to be updated does not exist, and `500 INTERNAL SERVER ERROR` for other errors. |
| DELETE    | Deletes a resource.                                          | `200 OK` or `204 NO CONTENT` if the resource has been deleted successfully, `404 NOT FOUND` if the resource to be deleted does not exist, and `500 INTERNAL SERVER ERROR` for other errors. |

## Principle 4 - Resource can have multiple representations

A key feature of a resource is that it may be represented in a different format from the one in which it is stored. This, it can be requested or created in different representations. 

## Principle 5 - Communicate with resources in a stateless manner

Resources manipulation operations through HTTP request should always be considered atomic. All modifications of a resource should be carried out within an HTTP request in an isolated manner. After the request execution, the resource is left in a final state; this implicitly means that partial resource updates are not supported. You should always send the complete state of the resource.

