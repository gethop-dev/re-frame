## SSR support with multithreading dynamic app-db

In order to support server-side rendered applications, using Isomorphic Rendering approach, we have modified re-frame to support dynamic, multi-threading app-db instances, so we can have an isolated app-db per HTTP request, when serving server side rendered content.

The rationale and inspiration behind this idea can be found on [this blog post](https://techascent.com/blog/isomorphic-rendering.html), written by Techascent. There you will find that they have also used their own fork of re-frame, but in their case, some more modifications were needed in order to use re-frame event handlers to populate app-db in the backend side, for the SSR rendering.

However, in our approach we have not needed that feature, as we just populate app-db by re-using same services we use for our API requests, which are executed in sequence.

