# Roy's Note W01D2

## Scope
global and local

A *globally-scoped* variable is available everywhere in the code, whereas a *locally-scoped* variable would only be available within the function in which it's defined.

# 5 rules for defining functions

1. Give your functions precise verb/action based names
2. Use camelCasedNames (like this one)
3. Properly indent the function code

4. Functions should focus on a single task: returning a value or causing a side effect. Break your function into additional smaller functions if you find it doing two or more things
   * One single task could be to compute and return a value (eg: zeroPad)
   * Another single task could be to perform a side effect such as logging a message to the screen (eg: printFarmInventory)

5. Data needed by Functions should be passed in as parameters/arguments (i.e. local scope) instead of being accessed directly

## Tips
exit the command line
```
process.exit
```

## KeyWords

**Pseudocode**
**template literal**
**cheat sheet**