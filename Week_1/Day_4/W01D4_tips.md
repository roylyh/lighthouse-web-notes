# Roy's Notes

## function
- function declaration
```javascript
function func() {
  xxx
}
```
- funciton expression
```javascript
cont func = function() {
  xxx
}
```
*Named Function Expression* -- easy to debug

## arrow function
The handling of this is also different in arrow functions compared to regular functions.

In short, with arrow functions there are no binding of **this**.

## Callback & Higher Order Functions
```
const func1 = function (param,callback) {
  callback;
}
```
*func1 is a higher order fundcion*  
Functions that take in callbacks are referred to as Higher Order Functions. Higher-Order functions are any functions which operate on other functions. (Could a function which will return a function)

## Higher Order Functions within Array

- forEach: loop every element of the array
- filter: return a new array which filter by true
- map: return a new array while loop every element of the array
- reduce: return a single value;  it executes a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. 
- sort: order the array by the return value

**reduce**
``` javascript
const array1 = [1, 2, 3, 4];

// 0 + 1 + 2 + 3 + 4
const initialValue = 0;
const sumWithInitial = array1.reduce(
  (accumulator, currentValue) => accumulator + currentValue,
  initialValue
);

console.log(sumWithInitial);
```
**sort**  
Sorting an array lexicographically (aka "alphabetically" or in dictionary order) is easy to do. Just call array.sort() without any parameters passed in:
```javascript
var myarray=["Bob", "Bully", "Amy"]
myarray.sort() // Array now becomes ["Amy", "Bob", "Bully"]
```
```javascript
function sortfunction(a, b){
    //Compare "a" and "b" in some fashion, and return -1, 0, or 1
}
array.sort(sortfunction)
```
- Less than 0: Sort "a" to be a lower index than "b" ascending order
- Zero: "a" and "b" should be considered equal, and no sorting performed.
- Greater than 0: Sort "b" to be a lower index than "a".
descending order

**comparator of object**
```javascript
// custom comparator
const students = [
  { id: 1, name: "bruce", age: 40 },
  { id: 2, name: "zoidberg", age: 22 },
  { id: 3, name: "alex", age: 22 },
  { id: 4, name: "alex", age: 30 },
];

const advanceSort = function (array, callback) {
  return array.sort(callback);
};

const sortRule = function (a, b) {
  if (a.name > b.name) {
    return 1;
  } else if (a.name < b.name) {
    return -1;
  } else {
    return b.age - a.age;
  }
};

console.log(advanceSort(students,sortRule));
```