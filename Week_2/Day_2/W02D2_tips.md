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

## Asynchronous Programming (event loop)
[JS异步编程（一）事件循环模型](https://juejin.cn/post/7051465463422779400)  
some concept   
Call stack; Web Apis; Callback Queue; Event Loop;  
1. deal with call stack(main thread)
2. Asynchronous Function go to Web Apis
3. Finish operation(like fetch data) then callback function go to Queue
4. New Promise(func1).then(func2)  func1 is a static function run in the main thread, and func2 is a callback run in the jobqueue -- timeout is in the taskqueue, the event loop priorities dequeuing jobs from the job queue(wihich stores the fulfilled promises' callbacks) over the tasks from the task queue(which stores timed out callbacks) 
5. event loop dequeue the jobs and tasks  
![eventloop1](https://github.com/roylyh/lighthouse-web-notes/blob/aca2226f0b482016c048b7582557ae0906765285/docs/eventloop1.png)![eventloop2](https://github.com/roylyh/lighthouse-web-notes/blob/db909c6d18853bc57b565dbbb1c206fec33d368c/docs/eventloop2.png)

```javascript
 console.log('1');
    // s1
    setTimeout(function () {
      console.log('2');
      new Promise(function (resolve) {
        console.log('3');
        resolve();
      }).then(function () {
        // p2
        console.log('4')
      })
      // s3
      setTimeout(function () {
        console.log(5);
      })
    })
    new Promise(function (resolve) {
      console.log('6');
      resolve();
    }).then(function () {
      // p1
      console.log('7')
    })
    // s2
    setTimeout(function () {
      console.log('8');
      new Promise(function (resolve) {
        console.log('9');
        resolve();
      }).then(function () {
        // p3
        console.log('10')
      })
    })

// 输出的顺序就是 1,6,7,2,3,4,8,9,10,5。在Chrome控制台验证也是这个顺序。

document.addEventListener('click', function () {
      Promise.resolve().then(() => console.log(1));
      console.log(2);
    })
    document.addEventListener('click', function () {
      Promise.resolve().then(() => console.log(3));
      console.log(4);
    })

// 正确输出顺序是 2,1,4,3
```