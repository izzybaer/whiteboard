You have an integer array which contains numbers from 1 to 100 but one number is missing, you need to write a function `calculateMissing = (array) => {...}` to find that missing number in an array.

```javascript
// function to calculate missing number in an array of numbers 1 - 100

const calculateMissing = (array) => {
  return array.reduce((a, c) => a + c);
}

// print an array with numbers 1 to 100 comma separated
[...Array(101).keys()].map(x => ++ x).reduce((acc, cur) => acc + cur);

```
* One trick to solve this problem is to calculate sum of all numbers in the array and compare with expected sum, the difference would be the missing number.
