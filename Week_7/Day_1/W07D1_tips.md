# React

## React State
[techpedia a good source website](https://www.techopedia.com/)

## useState Hook
fancy buttons - example project
```js
toggle
const switchLight = () => setLight((light === "on") ? "off" : "on");
```

## controlled components
When we create components that override HTML form elements to let React control their state, we call them controlled components.  
The pattern involves:  
- Set a variable that is stored in state as the value attribute on the form element.
- Use an onChange event that uses the setter of your state to set a new value when the input changes.
```js
const [word, setWord] = useState("");
<input
  value={word}
  onChange={(event) => setWord(event.target.value)}
  placeholder="Please enter a word"
/>
```
For more information on Forms in React, read the [official docs](https://legacy.reactjs.org/docs/forms.html).

## Fragment
Unlike a <div>, a React <Fragment> does not create any extra DOM nodes, which can clutter up your HTML output and cause problems with your layout.
