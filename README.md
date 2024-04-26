Work in progress... https://al-nextjs-dashboard.vercel.app/dashboard

## Acme dashboard full web application

<img src="./public/hero-desktop.png" alt="Acme full web application" style="max-width: 100%;"/>

Next.js App Router Course. See the [course curriculum](https://nextjs.org/learn) on the Next.js Website. Course covers the following topics:

- CSS styling - style application with Tailwind and CSS modules
- Optimizing fonts and images
- Creating Layouts and Pages
- Navigation Between Pages using Link component
- Fetching Data
- Static and Dynamic Rendering
- Streaming: improve the app's loading experience with streaming and loading skeletons
- Search and Pagination using Next.js APIs
- Mutating data using React Server Actions and revalidating the cache
- Handling errors gracefully with error.tsx and notFound
- Implement server-side form validation and improve accessibility in forms

### Few things done to optimize data fetching in the application:

1. Created a database in the same region as the application code to reduce latency between the server and database.
2. Fetched data on the server with React Server Components. This allows you to keep expensive data fetches and logic on the server, reduces the client-side JavaScript bundle, and prevents the database secrets from being exposed to the client.
3. Used SQL to only fetch the data you needed, reducing the amount of data transferred for each request and the amount of JavaScript needed to transform the data in-memory.
4. Parallelize data fetching with JavaScript - where it made sense to do so.
5. Implemented Streaming to prevent slow data requests from blocking the whole page, and to allow the user to start interacting with the UI without waiting for everything to load.
6. Moved data fetching down to the components that need it, thus isolating which parts of the routes should be dynamic in preparation for Partial Prerendering.

### Search and pagination implementation:

1. Handle search and pagination with URL search parameters instead of client state.
2. Fetched data on the server.
3. Use the useRouter router hook for smoother, client-side transitions.
