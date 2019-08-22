# The REST goals

These are the goal that we can achieve when the REST principles are follow:

- Separation of the representation and the resource
- Visibility
- Reliability
- Scalability
- Performance

## Separation of the representation and the resource

A resource is just a set of information, and as defined by principle 4, it can have multiple representations; however, its state is atomic. It is up to the caller to specify the desired media type with the `Accept` header in the HTTP request, and then it is up to the server application to handle the representation accordingly, returning the appropriate content type of the resource together with a relevant HTTP status code.

## Visibility

REST is designed to be visible and simple. Visibility of the service means that every aspect of it should be self-descriptive and follow the natural HTTP language according to principles 3, 4, and 5.

## Reliability

Before talking about reliability, we need to defined which HTTP methods are safe and which are idempotent in the REST context.

> - An HTTP method is considered to be safe provided that, when requested, it does not modify or cause any side effects on the state of the resource.
>
> - An HTTP method is considered to be idempotent if its response stays the same, regardless of the number of times it is requested, an idempotent request always give back the same response, if repeated identically.

The following list shown which HTTP methods are safe and which are idempotent:

| HTTP method | Safe | idempotent |
| ----------- | ---- | ---------- |
| GET         | Yes  | Yes        |
| POST        | No   | No         |
| PUT         | No   | Yes        |
| DELETE      | No   | Yes        |

## Scalability and performance

Is important to stress the need of stateless RESTFul application because scaling application that have a state is difficult to achieve,   especially when zero or close-to-zero operational downtime is expected. That's why staying stateless is crucial for any application that needs to scale. 

Scalability is all about serving all your clients in an acceptable amount of incoming requests.

Performance is measured by the time needed for a single request to be processed, not by the total number of request that the application can handle.