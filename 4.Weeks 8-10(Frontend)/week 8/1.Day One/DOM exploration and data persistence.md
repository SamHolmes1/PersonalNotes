- Span tags - normally used to access a specific piece of text i.e
```html
<p>moods: <span id="mood-count"></span>0</p>
```

```js
const moodCount = document.getElementById("mood-count");

const moodOptions = [...document.getElementsByClassName("mood-option")];

const moodContainer = document.querySelector(".moodcontainer")
moodOptions.forEach((moodOption) => {
	moodOption.addEventListener("click", (event) => {
		const selectedMood = event.target.innerText;
		moodCount.innertext++;
		
		const templateText = `Thanks for voting ${selectedMood}`;
		const h3Element = document.createElement("h3");
		h3Element.innerText = templateText;
		moodContainer.appendChild(h3Element);


	})
})


moodCount.innerText = 0;
```
