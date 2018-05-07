# Problem Statement
Given an array of integers, find the highest product you can get from three of the integers.

## Constraints (Don't mention this to students, but let's guide them to a O(n) solution if we see them going the O(n^2) route.
Implement a function with a O(n) time complexity and a O(1) space complexity.

# Follow Up Question

__Don't ask this to students until they are done with the problem__

If our highest product is really big, it could overflow. How should we protect against this?

*Answer : There are NPM packages and libraries to deal with Big Numbers in JS*

```javascript

let integerArray = [1, 4, 5, 7, 2, 9];

const highestOfTwo = (integerArray) => {
  if(!Array.isArray(integerArray))
    throw new TypeError('expecting an array');

  if(integerArray.length < 2)
    throw new Error('expecting an array with at least two elements');

  let highestNumberSoFar = Math.max(integerArray[0], integerArray[1]);
  let highestProductSoFar = integerArray[0] * integerArray[1];

  for(let i = 2; i < integerArray.length; i++){
    let currentNumber = integerArray[i];

    highestProductSoFar = Math.max(highestProductSoFar, highestNumberSoFar * currentNumber);

    highestNumberSoFar = Math.max(highestNumberSoFar, currentNumber);
  }

  return highestProductSoFar;
  console.log(highestProductSoFar);
};



// different solution
// run Math.max on entire array using ...array
// returns the highest number, pop it off
// run Math.max on entire array (minus highest number you popped off)
// returns the highest number, now we have the two highest numbers
// save them in a variable (each high number) multiply and return

highestOfTwo(integerArray);
```
