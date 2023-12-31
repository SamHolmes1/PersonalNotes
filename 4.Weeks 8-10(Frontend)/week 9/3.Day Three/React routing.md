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

TIP: use CSS to create borders around components to help you see what's going on and what's being rendered 


```jsx
//App.jsx

import { BrowserRouter, Route, Routes } from "react"


return App() {

	return(
		<BrowserRouter> 
			<div className="app">
				<Header /> {/* Rendered in all views */}
				<Routes> 
					<Route path="/" element={<Home />} />
					<Route path="/:colour" element={<Colour />} />
				</Routes>
			</div>
		</BrowserRouter>
	)

}
```


```jsx
//Colour.jsx
import  useParams form 'react-router-dom'

const { colour } = useParams();

const Colour = () => {
	return(
		<div className="content blue">
			<p>{colour}</p>
		</div>
	)

}

```