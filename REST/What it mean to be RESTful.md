# What it means to be RESTful

## What is REST?

REST stands for **representational state transfer**, and is a set of **architectural styles** that dictates the manner and patterns in which you construct your API. 

There are six requirements for REST:

- Client-server: Defines a clear **separation of concerns (SoC)** between client and server. The client should provide the user interface, while the server provides the data.
- Stateless: No transient information about the client should be held on the server. In other words, the server should not persist client sessions; if sessions need to be persisted, it must be done on the client. Any request that arrive at the server must contain all the information required to process that request. 
- Cacheable: If the response is going to be the same given the same request, then that response should be cached by the client and/or any intermediaries. A RESTful architecture requires that the response message must include an indication of whether the response should be cached, or not, and if so, for how long.

## What REST is not

REST is an **architectural style**, and does not impose low-level implementation details. REST is a generic set of rules/patterns that you can apply to any API.



