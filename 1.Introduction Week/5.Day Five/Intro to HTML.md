# Learning Objectives
- Understand what HTML is and why it is important
- know the basic structure of an HTML document
- identify common HTML elements
- understand the concept of semantic HTML
- know some basic accessibility practices


Think of these three languages Like a house

# HTML
- Markup Language
- Foundations and walls of the house, which give it structure and hold it together
# CSS
- Rule based language
- The pain, wallpaper, carpets and painting you'd use to make the house look nice
# JS
- Programming Language
- - the cooker, TV microwave, hairdryer. The thing that makes it do stuff and have functionality




# HTML Learning

- In VSCode, you can type ! into an empty document to get a basic structure for a HTML document. this is an emmet abbreviation(?)
- <mains>Is to denote the main bulk of your </main>
- command pallet: emmet wrap with abbreviation
- tags that don't modify text often don't have a closing tag. Called replaceable tags
- You can give tags more information using attributes
- lorem is an emmet abbreviation to write lorem ipsum
- When we wrap something in tags we put it in a box, this is the box model. We can style these boxes later

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Document</title>
</head>
<body>
	<!-- This is a comment! -->
	<header>
		<h1>My Page</h1>
	</header>
	<main id="main-content">
		<section>
			<h2>Profile</h2>
			<p>
			This is the paragraph with a bunch of text.
			This is a bit more.
			</p>
			<p>
			This is the paragraph with a bunch of text.
			This is a bit more.
			</p>
			<p>
			This is the paragraph with a bunch of text.
			This is a bit more.
			</p>
		</section>
		<section>
			<h2>My Likes</h2>
			<p>
			Here are some things I like 
			</p>
			<ol>
				<li>Music</li>
				<li>Food</li>
				<li>Sleep</li>
			</ol>
		</section>
		<section>
			<h2>Photo Gallery</h2>
			<img src="image.jpg" alt="this is an image">
		</section>
	</main>
	<footer>
		<nav>
			<ul>
				<li>Check out my <a href="https://instagram.com" target"/blank"=>Instagram</a></li>
				<li><a href="#main-content">Back to main content</a></li>
			</ul>
		</nav>
	</footer>
</body>

</html>
```

# Accessibility
- Legal requirements - legal requirement to meet basic accessibility requirements
- inclusive design
- SEO benefits

- Semantic HTML
- Ordered headings
- Alt text for images
- Form labels
- Readable text
- Keyboard navigation
- ARIA - accessible rich internet application - Check docs