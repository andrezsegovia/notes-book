# Middleware

It is a subset of chained functions called by the `Express.js` routing layer before a user-defined handler is invoked. Middleware functions have full access to `request` and `response` objects and can modify either of them. The middleware chain is always called in the exact order in which it has been defined. Once a middleware function finishes, it calls the next function in the chain by invoking its next argument as a function. After the complete chain gets executed, the user-defined request handler is called.

Here are the basic rules that apply to the middleware chain:

> - A middleware function has the following signature: `function (request, response, next)`.
> - Middleware function are executed in the exact order in which they have been added to the application chain. 
> - Middleware functions use their third parameter, `next`, as a function to indicate that they have completed their work and to exit. 