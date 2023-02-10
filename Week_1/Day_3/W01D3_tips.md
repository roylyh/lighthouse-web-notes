# Roy's Note W01D1

## Primitive Data Types  
- undefined
- null
- boolean
- string
- number
- symbol  

**Objects Are Not Primitives**

## Object

Object.keys(obj) return array of keys  
obj[key] key could be a variable or space in the string  
Operate the value in the object or insert a property and value
``` javascript
if (obj[key]) {
  obj[key]++;
} else {
  obj[key] = 1;
}
```
Find the key with the highest value
``` javascript
const numberObj = {
  a: 1,
  b: 50,
  c: 12
}

function getMaxValueKey(obj) {
  return Object.keys(obj).reduce((a, b) => obj[a] > obj[b] ? a : b);
}

getMaxValueKey(numberObj) // 'b'
```

## tips

[pythontutor](https://pythontutor.com/) A good place to see the process of the program

**object** *this*
```
cont obj = {
  name: xxx;
  fun: function() {
    console.log(this.name);
  }
}
``` 

**ParseInt('25 times')** output 25