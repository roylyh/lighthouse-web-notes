# Roy's Notes

## Why do we want to use callbacks?
- It is to 'abstract out' some computation, i.e. to leave it undefined while we write a function
- That wraps logic around that 'abstracted' computation  
**For functions executed by the Event Loop, you cannot retrieve the return value directly**

## wait for serveral seconds
```javascript
function sleepFor(sleepDuration) {
  const newObj = new Date();
  const now = newObj.getTime();
  while (new Date().getTime < now + sleepDuration) {
    donothing;
  }
}
```


## Advanced Reading
[**event loop blocked**](https://snyk.io/blog/nodejs-how-even-quick-async-functions-can-block-the-event-loop-starve-io/)
