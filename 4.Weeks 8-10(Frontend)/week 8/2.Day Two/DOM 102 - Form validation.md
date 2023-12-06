- Understand how forms work
- Revise DOM methods and semantic HTML
- Know how to provide user interface validation 
- know how to use form attributes and submit handlers to utilise form data

# Notes
- Labels can be used for accesibility
- When you create a button as a child of a form, the default behaviour submits the data from the form

# Example

```html
<!Doctype html>
<html lang="en">
	<head>
		<title>Signup</title>
		<link rel="stylesheet" href="index.css" />
		<script src="index.js" defer></script>
	</head>
	<body>
	<h1>Sign up</h1>
	<form class = "signup-form" id="signup-form" method="GET"                        action="./welcome.html">
		<label class="signup-label" for="username">Usernam:</label>
		<input type="text" class="signup-input" placeholder="username..."                id="username" name="username"/>
		<label class="signup-label" for "phonenumber">Phone number</label>
		<input type="tel" class="signup-input" name="phonenumber"                        placeholder="1234556" id="phonenumber"/>
		<button class="signup-submit">Sign up</button>
	</form>
	</body>
</html>
```

```js
// --- GET ELEMENTS ---
const userNameInput = document.getElementById("username");
const phoneNumberInput = document.getElementById("phonenumber");
const signUpForm = document.getElementById("signup-form");


// --- ADD LISTENERS ---
userNameInput.addEventListener("keyup", validateUserName);
phoneNumberInput.addEventListener("blur", validatePhoneNumber); // Blur occurs when we click off of the field. when we lose "focus"
signUpForm.addEventListener("submit", handleFormSubmit)

// --- DEFINE EVENT HANDLERS ---
function handleFormSubmit(event){
	const inputs = [...document.getElementsByClassName("signup-input")];
	const areAllValid = inputs.every((input) => {
		return input.classList.contains("valid");
	}) // returns a boolean
	if(!areAllValid){
		event.preventDefault(); // preventDefault will stop the default behaviour
	}
}

function validateUserName(event){
	const userName = event.target.value;
	const regex = /\d/;
	if(regex.test(userName)){
		userNameInput.classList.add("valid"); // .valid is defined in the css
		userNameInput.classList.remove("invalid");
	}else{
		userNameInput.classList.remove("valid"); // .valid is defined in the css
		userNameInput.classList.add("invalid");
	}
}

function validatePhoneNumber(event){
	const phoneNumber = event.target.value;
	const regex = /^\d+$/;
	if(regex.test(phoneNUmber)){
		phoneNumberInput.classList.add("valid");
		phoneNumberInput.classList.remove("invalid");
	}else{
		phoneNumberInput.classList.remove("valid");
		phoneNumberInput.classList.add("invalid");
	}
}

```

```css
.valid{
	background-color: #green
}

.invalid{
	background-color: #red
}
```