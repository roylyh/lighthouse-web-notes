# Roy's note

## Tree Data Structure
[Tree](https://web.compass.lighthouselabs.ca/517fb741-0682-45ff-b86b-b4bb25833dfa)

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