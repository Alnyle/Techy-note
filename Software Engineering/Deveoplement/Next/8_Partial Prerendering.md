uses React's [Suspense](https://react.dev/reference/react/Suspense) (which you learned about in the previous chapter) to defer rendering parts of your application until some condition is met (e.g. data is loaded).

The Suspense fallback is embedded into the initial HTML file along with the static content. At build time (or during revalidation), the static content is **prerendered** to create a static shell. The rendering of dynamic content is **postponed** until the user requests the route.

Wrapping a component in Suspense doesn't make the component itself dynamic, but rather Suspense is used as a boundary between your static and dynamic code.

Partial Prerendering in React, which utilizes React's `Suspense` component. Here's a breakdown of what you've described:

1. **Partial Prerendering**: This technique is used to prerender parts of an application while deferring other parts until certain conditions are met, such as data being loaded. This can help in optimizing the initial load time of an application by serving static content immediately while waiting for dynamic content to be ready.
    
2. **Suspense**: The `Suspense` component in React is a mechanism to handle asynchronous operations like data fetching. It allows you to specify a fallback UI (like a loading spinner) to be shown while waiting for dynamic content to load. In the context of Partial Prerendering, `Suspense` serves as a boundary between prerendered static content and content that needs to be dynamically fetched or rendered.
    
3. **Prerendering Process**: During the build process, static content is rendered into HTML, which creates a static shell. This static content is included in the initial HTML file served to the user. When the user navigates to a route, the dynamic content that was deferred by `Suspense` is then fetched and rendered.
    
4. **Component Dynamics**: Wrapping a component in `Suspense` doesn't inherently make the component dynamic. Instead, `Suspense` is used to manage the loading state and the transition between static and dynamic content.
    

This approach is particularly useful for improving performance in web applications by minimizing the time it takes to deliver content to users while ensuring that dynamic parts of the application are loaded efficiently when needed.

## [Summary](https://nextjs.org/learn/dashboard-app/partial-prerendering#summary)

To recap, you've done a few things to optimize data fetching in your application:

1. Created a database in the same region as your application code to reduce latency between your server and database.
2. Fetched data on the server with React Server Components. This allows you to keep expensive data fetches and logic on the server, reduces the client-side JavaScript bundle, and prevents your database secrets from being exposed to the client.
3. Used SQL to only fetch the data you needed, reducing the amount of data transferred for each request and the amount of JavaScript needed to transform the data in-memory.
4. Parallelize data fetching with JavaScript - where it made sense to do so.
5. Implemented Streaming to prevent slow data requests from blocking your whole page, and to allow the user to start interacting with the UI without waiting for everything to load.
6. Move data fetching down to the components that need it, thus isolating which parts of your routes should be dynamic.

In the next chapter, we'll look at two common patterns you might need to implement when fetching data: search and pagination.