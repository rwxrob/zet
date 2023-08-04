# The kubectl command does not create API queries in logs

Here's what ChatGPT had to say:

By default, when you run `kubectl` commands, it does not generate API queries that would be logged in the API server logs for Kubernetes. The primary reason for this is that `kubectl` communicates with the API server using the Kubernetes API directly rather than making HTTP requests to the server.

When `kubectl` is executed, it interacts with the Kubernetes API by sending API requests over HTTPS using the client-go library. It uses a library function rather than making direct HTTP requests to the API server. Consequently, the actual HTTP requests made by `kubectl` are not visible in the API server logs.

However, some information regarding the `kubectl` commands can be found in the API server logs. The API server logs record events related to authentication, authorization, and admission control, which can provide insights into the execution of `kubectl` commands. Additionally, Kubernetes events and audit logs may also contain relevant information about the `kubectl` commands performed.

If you need a more detailed and comprehensive log of `kubectl` commands, you can enable `kubectl` audit logging on the API server. With audit logging enabled, all `kubectl` commands will be logged, including the HTTP requests made by `kubectl`, allowing you to track and monitor the actions performed by `kubectl` in your Kubernetes cluster.

