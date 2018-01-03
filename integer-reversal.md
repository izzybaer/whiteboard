integer reversal - you cannot use a string at all you must only use integers

given an integer, return an integer that is the reverse ordering of numbers

```javascript
const reverseInt = (n) => {
  let reversed = n.toString().split('').reverse().join('');

  return parseInt(reversed) * Math.sign(n);
}

reverseInt(-987); // prints -789
```

```javascript
// izzy's ultra fancy BS solution using toString

const reverseInt = (n) => parseInt(n.toString().split('').reverse().join('')) * Math.sign(n);

reverseInt(7583); // prints 3857
```

```javascript
// second fancy solution without using toString
// use Math.sign() to keep negatives
const reverseInt = (n) => Math.sign(n) * Number(('' + Math.abs(n)).split('').reverse().join(''));

reverseInt(4583); // prints 3854
```

```javascript
// not using toString
const reverseInt = (n) => {
  let reversed = 0;

  while(n !== 0){
    reversed = (reversed * 10) + (n % 10);
      n = Math.floor(n/10);
  }
  return reversed;
}

reverseInt(459); // prints 954
```
