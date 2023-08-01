# Use context.Abort for middlewares in gin

When creating a custom middleware for gin, remember to call the abort method on the context rather
than calling an empty return on the method. Otherwise, the request will still go to the handler.
There are also some useful methods as well such as AbortWithError that will accept an error type to
output unless you already have error helpers to output.
