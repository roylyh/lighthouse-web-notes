# Roy's Note

## JSON
It stands for JavaScript Object Notation, and it's actually a subset of the JavaScript language.  
JSON is built on two structures:

- A collection of name/value pairs.  
- An ordered list of values.

JSON.parse()
- Parse a string as JSON, optionally transform the produced value and its properties, and return the value.

JSON.stringify()
- Return a JSON string corresponding to the specified value, optionally including only certain properties or replacing property values in a user-defined manner.

## Creating Promesies
```javascript
let creditLimit = 200;

/*
 * Input: number of dollars to loan out
 * Returns: Promise of loan which may or may not fulfill, based on remaining credit.
 * If creditLimit is less than the requested amount, only the remaining limit is loaned out, otherwise the full amount is loaned out. If $0 remain in the limit, the loan request is rejected (error!).
 */
const loanOut = function(amount) {
  return new Promise((resolve, reject) => {
    if (creditLimit <= 0) {
      reject("Insufficient Funds");
    } else if (creditLimit < amount) {
      resolve(creditLimit);
      creditLimit = 0;
    } else {
      creditLimit -= amount;
      resolve(amount);
    }
  });
};

console.log("Asking for $150, which should be okay ...");
loanOut(150)
  .then((amountReceived) => {
    console.log(`\t-> I got $${amountReceived} loan from the bank! Remaining Credit Limit: $${creditLimit}`);
    return creditLimit;
  })
  .catch((err) => {
    console.log(`\t-> Error: ${err}!`);
  });
```