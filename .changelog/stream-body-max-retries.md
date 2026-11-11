fix(client): warn when an explicit maxRetries is ignored for a stream body

A request whose body is a `ReadableStream`, an async iterable or an iterator is sent once and never retried. The client now logs a warning when the caller set a positive `maxRetries` on the client or the request for such a body, and the `maxRetries` doc comments say so.
