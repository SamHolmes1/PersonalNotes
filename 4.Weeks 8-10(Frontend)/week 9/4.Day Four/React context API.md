- Understand when you should use ocntext
- Understand how to create a context
- Know how to provide values to a context
- Know how to consume values from a context (useContext)

# React context
- Alternative to props - but NOT a replacement
- It can make your components less reusable
- it should be used sparingly
- Used for values that are truly global
	- User
	- Theme
	- Language


```jsx
//UserContext.jsx
import { createCopntextm useState } from 'react';

// Create a context to be used by our components
export const UserContext - createContext();

// Create a component that will provide a value to our context

export const UserProvider = (props) => {
	const [user, setUser] = useState("Obi")
	return <UserContext.provider value={{ user, setUser}}>
	{props.children}
	</UserContext.provider>
};


```


```jsx
// App.jsx
import { UserProvider } from "UserContext"

return <UserProvider>
		   <Components />
		   <Components />
		   <Components /> 
	   </UserProvider>

```