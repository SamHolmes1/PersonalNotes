- Understand the key difference betyween SPAs and MPAs
- Understand how to plan an app with different routes
- Know how to use React Router eo emulate a MPA
- Know how to conditionally render componenets using RR
- Know how to access URL parameters using RR


# MPAs vs SPAs
## Multi page applications
- Sepeterate HTML pages
- Initial page is loaded based on the URL so is relatively quick
- Navigation triggers a new page request which must be fetched from the server
## Single Page Applications
- Single HTML page
- app is loaded on initial request so the first load may be slower
- Navigation updates component view which happens quickly


# React Router
- Library for handling routing in React apps
- Provdes a way to map different URLs to different components
- Enables the creation of multt-page=like experiences within a single-page application
- Allows us to define routers and associate them with specific components