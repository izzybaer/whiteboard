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
```javascript
// this method is the same but fancier

const reverseStr = (str) => str.split('').reverse().join('');

reverseStr('izabella'); // prints 'allebazi'
```
```javascript
// this method uses a for loop (for of syntax)
// can't use this syntax to loop through every 'so' many elements (third, fifth, sixth)

const reverseStr = (str) => {
  let reversed = '';

  for(let character of str){
    reversed = character + reversed;
  }
  return reversed;
}
reverseStr('izabella'); // prints 'allebazi'
```
```javascript
// this method is my favorite and super fancy
// this last method will use a complicated array helper

const reverseStr = (str) => return str.split('').reduce((a, c) => c + a, '');
  // takes all the values of the array and condenses them into one singular value

reverseStr('javascript'); // prints 'tpircsavaj'
```
