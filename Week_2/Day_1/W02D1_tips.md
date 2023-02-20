# Roy's Notes

## Caesar Cipher
```javascript
// key: how many steps will the character change
const encrypt = function(plaintext, key) {
  let result = "";
  for (let i = 0; i < plaintext.length; i++) {
    // 97 - 122 a - z
    if (plaintext.charCodeAt(i) > 96 && plaintext.charCodeAt(i) < 123) {
      const code = plaintext.charCodeAt(i) + key;
      result += String.fromCharCode(code > 122 ? (code - 122) % 26 + 96 : code < 97 ? (code - 97) % 26 + 123 : code);
    } else {
      result += plaintext.charAt(i);
    }
    
  }
  return result;
};

module.exports = { encrypt };
```

## Mocha & Chai

**Mocha**  
- A testing framework
- By default, looks in the test folder for test files to run
**Chai**
- An assertion library
- Chai offer three different interfaces: should, expect and assert
```javascript
// should
myVar.should.be.a('string');
myVar.should.equal('hello world');

// expect
expect(myVar).to.be.a('string');
expect(myVar).to.equal('hello world');

// assert
assert.typeOf(myVar, 'string');
assert.equal(myVar, 'hello world');
```

## module.export and require
```javascript
// adding new keys to module.exports
module.exports.myFunc = myFunc;
module.exports.myOtherFunc = myOtherFunc;

// overwriting module.exports object
module.exports = myFunc;
// or
module.exports = {
  myFunc,
  myOtherFunc
};

// basic require syntax
const myFunc = require('./myFunc');

// if the file exports an object, we can use ES6 destructuring
const { myFunc } = require('./myFunc');
```

## ignoring files/folders
- Sometimes there are files or folders that we do not want git to track for us
- These files might contain sensitive information such as passwords or API keys
- They might also be folders such as node_modules which should always be ignored
- We can tell git to ignore certain files/folders by using a special file called .gitignore (note the leading period)
- Any files that we specify inside of .gitignore will be ignored by git
```javascript
# inside .gitignore
node_modules
my-file.js
```

## useful links
- [Node Wrapper Function](https://nodejs.org/api/modules.html#modules_the_module_wrapper)
- [Chai: Differences between should, expect, and assert](https://www.chaijs.com/guide/styles/#differences)

How to use throw Error in Chai assertion
```javascript
// with argument
assert.throws(() => trickyCode({ veryTricky: true }), Error, "folder does not exist");
// without argument
assert.throws(trickyCode, Error, "folder does not exist");
```