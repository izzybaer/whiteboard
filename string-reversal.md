given a string return a new string with the order of characters reversed

```javascript

// this method is super easy but not as obvious
// first turn string into array
// call reverse() on the array
// join the array back into a string
// return the result

const reverseStr = (str) => {
  let arr = str.split('');
  return arr.reverse().join('');
}

reverseStr('izabella'); // prints 'allebazi'
```
