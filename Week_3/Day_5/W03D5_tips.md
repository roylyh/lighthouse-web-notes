# Roy's note

## Tree Data Structure
[Tree](https://web.compass.lighthouselabs.ca/517fb741-0682-45ff-b86b-b4bb25833dfa)

## test
The Object.entries() static method returns an array of a given object's own enumerable string-keyed property key-value pairs.  

The Object.fromEntries() static method transforms a list of key-value pairs into an object.
```javascript
const object1 = {
  a: 'somestring',
  b: 42
};

for (const [key, value] of Object.entries(object1)) {
  console.log(`${key}: ${value}`);
}

// Expected output:
// "a: somestring"
// "b: 42"

const entries = new Map([
  ['foo', 'bar'],
  ['baz', 42]
]);

const obj = Object.fromEntries(entries);

console.log(obj);
// Expected output: Object { foo: "bar", baz: 42 }

```

## tips
```
// run the test files seperately
npm test -- test/1*.js  # will run file test/1_addOffspring.js only
npm test -- test/2*.js  # will run file test/2_numberOfOffspring.js only
```

**mocha**
```javascript
describe("Vampire", function() {

  let rootVampire;
  // run the function automatically before everything
  beforeEach( function() {
    rootVampire = new Vampire("root");
  });

  describe("numberOfOffspring", () => {

    it("should get the correct number of offspring", () => {
      expect(rootVampire.numberOfOffspring).to.equal(0);
      rootVampire.addOffspring(new Vampire());
      expect(rootVampire.numberOfOffspring).to.equal(1);
      rootVampire.addOffspring(new Vampire());
      rootVampire.addOffspring(new Vampire());
      rootVampire.addOffspring(new Vampire());
      rootVampire.addOffspring(new Vampire());
      expect(rootVampire.numberOfOffspring).to.equal(5);
    });
  });
});
```