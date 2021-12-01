# One Way to Convert a String Boolean to Actual Boolean

This seems super trivial but I ran into a bug where an object's attribute was thought to be a boolean, when in reality
it was a string representation of the boolean. One of my comparison conditionals kept failing because no matter what,
the value was always truthy.

To fix, I just set my variable of a strong check (eg ===)

```js
// WHAT BROKE
const myVar = incomingBool; // could be 'true' or 'false'

// always evaluted to truthy since it's a string representation
if (incomingBool) { 
  doSomething();
 } 


// THE FIX
const myVar = (incomingBool === 'true'); // now I have an actaul boolean
...
```
