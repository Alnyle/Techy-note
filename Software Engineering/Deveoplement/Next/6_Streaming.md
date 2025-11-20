
## [What is streaming?](https://nextjs.org/learn/dashboard-app/streaming#what-is-streaming)

Streaming is a data transfer technique that allows you to break down a route into smaller "chunks" and progressively stream them from the server to the client as they become ready.

![[server-rendering-with-streaming.avif]]

By streaming, you can prevent slow data requests from blocking your whole page. This allows the user to see and interact with parts of the page without waiting for all the data to load before any UI can be shown to the user.

![[server-rendering-with-streaming-chart.avif]]

Streaming works well with React's component model, as each component can be considered a _chunk_.

There are two ways you implement streaming in Next.js:

1. At the page level, with the `loading.tsx` file.
2. For specific components, with `<Suspense>`.

in other streaming allow to load the page even the dynamic content don't full rendered

Yes, that's correct. In Next.js, streaming allows the server to send parts of the HTML to the client as they are generated, rather than waiting for the entire page (including all dynamic content) to be fully rendered. This can significantly improve the perceived performance of your application by allowing users to see and interact with the content that has already been rendered while other parts of the page are still being processed.

### How Streaming Works in Next.js:

- **Initial HTML Sent Early:** When a request is made, the server starts generating the HTML. As soon as some parts of the page are ready, they are sent to the client. This could include the static parts of the page, such as the header, footer, or any other content that doesn't rely on dynamic data.
    
- **Progressive Rendering:** As the server continues to generate dynamic content (like data fetched from an API or database), it streams these parts to the client as they become available. This allows the user to start interacting with the page sooner, even if some components are still loading.
    
- **Suspense and Streaming:** Next.js uses React's `Suspense` to manage streaming. Components that rely on dynamic data can be wrapped in `Suspense` boundaries. While waiting for the data to be fetched and the component to be rendered, the rest of the page can be streamed to the client. When the data is ready, the suspended component is rendered and added to the page.
    

### Benefits of Streaming in Next.js:

- **Faster Time to First Byte (TTFB):** By streaming the initial parts of the page as soon as they are ready, the browser can start rendering the page earlier, improving the TTFB metric.
    
- **Improved User Experience:** Users can start interacting with parts of the page even before all the data has been fully loaded, leading to a smoother and more responsive experience.
    
- **Progressive Loading:** Streaming allows for progressive loading of the page content, which is particularly useful for pages with large amounts of data or complex dynamic content.
    

### Example Use Case:

Imagine a blog page where the header, footer, and navigation are static, but the main content (like the article and comments) is fetched from a database:

- With streaming, the server could send the header and navigation to the client immediately.
- While the user sees the header and can start navigating, the article content is being fetched and streamed as soon as it's ready.
- Finally, comments are fetched and rendered as the user scrolls down.

In summary, streaming in Next.js improves perceived performance by allowing parts of a page to be rendered and interacted with before the entire page is fully loaded. This approach enhances the user experience, especially in applications with heavy dynamic content.


Yes, streaming in Next.js sends rendered components of a page part by part, progressively delivering content to the client as it becomes available.

Here’s how it works:

### 1. **Initial Request:**

- When a user requests a page, the server begins processing the request.
- Instead of waiting for the entire page to be fully rendered, the server starts sending parts of the HTML as soon as they are ready.

### 2. **Progressive Streaming:**

- **Static Components:** Static parts of the page that don’t depend on any asynchronous data (like the header, footer, or navigation) are often ready first. These components are sent to the client immediately.
- **Dynamic Components:** Components that rely on data fetching or other asynchronous operations are processed in the background. As each dynamic component is rendered, the server streams it to the client.

### 3. **Suspense Boundaries:**

- Next.js uses React’s `Suspense` to manage streaming. You can wrap dynamic components with `Suspense` boundaries.
- While the dynamic content inside a `Suspense` boundary is being fetched and rendered, the server continues to stream the rest of the content to the client.
- Once the data for a `Suspense`-wrapped component is ready, the server renders that component and streams it to the client as well.

### 4. **Client-Side Rendering:**

- On the client side, the browser progressively receives these chunks of HTML and renders them as they arrive.
- This means that users can start interacting with parts of the page while other parts are still loading.

### **Example Flow:**

1. **Initial HTML Sent:** The server sends the basic HTML structure, including static components like the header and navigation.
2. **Streaming Dynamic Content:** As the server fetches data for dynamic components (like a blog post or user comments), it streams these components to the client as soon as they are rendered.
3. **Final Render:** Eventually, the entire page is rendered, but users don’t have to wait for everything to load before they can start interacting with the page.

### **Benefits:**

- **Faster Perceived Load Time:** Users see content sooner because parts of the page are rendered and displayed progressively.
- **Improved User Experience:** Users can interact with the parts of the page that are ready, rather than waiting for the entire page to load.
- **Efficient Data Handling:** Streaming allows the server to handle data fetching more efficiently, especially for pages with complex or heavy content.

### **In Summary:**

Yes, streaming in Next.js sends rendered components part by part, allowing the page to be progressively loaded and rendered on the client side. This improves the user experience by reducing the time it takes for users to see and interact with content.