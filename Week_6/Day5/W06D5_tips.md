# React Fundamental

## What is react?
- React makes it painless to create interactive UIs. Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes.
- Declarative views make your code more predictable and easier to debug.  
(Always start component names with a capital letter.)  
Most applications call ReactDOM.render(element, container) a single time to render the application.  

[format of date (date-fns)](https://date-fns.org/v2.30.0/docs/format)  
1. All tags must be closed
2. A child tag must close before its parent
3. All JSX expressions must result in one root level element
4. No HTML comments
```javascript
return (
  <div>
    <!--- Not allowed --->
    {/* Allowed */}
  </div>
)
```

## create-react-app
The <span style="color:pink">*create-react-app*</span> package is a tool that enables us to create a fully fledged React app in one command! 

## nvm
Node Version Manager (NVM), as the name implies, is a tool for managing Node versions on your device.  
```scripts
nvm install latest
nvm install 16
nvm install vX.Y.Z
nvm use vA.B.C
nvm alias default 16
```

## server
```
npm install -g serve
```
To see the files that we will be creating in the browser, we can use an npm package to serve our static files.  
Navigate to the folder html-version in the terminal and type serve.

## Event Handling In React
```javascript
1.
<button onClick={() => console.log("Button Clicked")}>
  Click me!
</button>
2.
<button onClick={doStuff}>Click me!</button>
3.
<div onClick={(event) => {
    console.log(`The mouse coordinates of this click event are: x: ${event.screenX} and y: ${event.screenY}`);
  }}></div>
```
- onClick Event Handler  
This event handler will listen to *click* events on clickable elements, like a button. Using the event parameter will give access to information about the event, like **mouse position**, **timestamp**, etc.  
- onChange Event Handler  
This event handler will listen to change events on input elements, like an input or a textarea element. Using the event parameter will give access to information about the event, like the **name of the input** and the **value that the user typed or selected**.  
- onSubmit Event Handler  
This event handler will listen to submit events on submittable elements, like a form. Using the event parameter will give access to information about the event, like the **content of the form**, and a method to **prevent the default behavior of a form submission**.

**[JavaScript Patterns For React](https://reacttraining.com/blog/javascript-the-react-parts)**

## React Project
tourney-matches (basic knowledge of React Props)
- Conditional Rendering
```js
if(props.yourName) {
      <h1>Hello, {props.yourName}.</h1>
    } else {
      <h1>Sorry, you don't seem to have a name.</h1>
    }
```
- Ternary Operator
```js
function Hello(props) { 
// CORRECT: Ternary is allowed. One of the two <h1s> will be rendered
  return (props.yourName ? <h1>Hello, {props.yourName}.</h1> : <h1>Sorry, you don't seem to have a name.</h1>);
}
```
- Short Circuit Evaluation
```js
function Hello(props) { 
  return (props.yourName && <h1>Hello {props.yourName}</h1>);
}
```