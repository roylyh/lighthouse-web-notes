# Roy's Notes

## Types of Testing
- Unit Testing  
*Unit testing* is the practice of testing small pieces of code, typically individual functions, alone and isolated. If your test uses some external resource, like the network or a database, it’s not a unit test.
- Integration Testing  
*Integration testing* is to test how parts of the system work together – the integration of the parts. 
- Functional Testing  
*Functional testing* is also sometimes called E2E testing, or browser testing. Functional testing is defined as the testing of complete functionality of some application.

## BDD
*BDD* or *Behavior Development* is a process that emerged from test-driven development process. The topic of BDD covers the entire life cycle of the app development process, from planning the project to writing the code.

**Testing Framework** [mocha](https://mochajs.org/)  
**Assertion Library** [chai](https://www.chaijs.com/)
```javascript
npm init
npm install mocha@9.2.2 chai --save-dev

// package.json
"scripts": {
    "test": "./node_modules/mocha/bin/mocha"
  },

// mkdir test && write the test file inside
const chai = require('chai');  // import the chai library
const assert = chai.expect;  // establish a variable to be used in our tests
const validator = require('../javascript/groupValidator.js'); // import the file where our function lives
describe("The function groupValidator()", () => {
    // this is where we put our tests.
    it("should return true if there are between 2 and 5 group members", () => {
    assert(validator.isGroupValid(["a", "b", "c"])).to.be.true
  });
});
```