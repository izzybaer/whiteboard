write a function fizzBuzz that console logs the numbers from 1 to n. For multiples of 3 print "fuzz" instead of the number and for multiples of 5 print "buzz" instead of the number. Numbers that are multiples of both 3 and 5 print "fizzbuzz"


```javascript
const fizzBuzz = (n) => {
  for(let i = 1; i <= n; i++){
    if(i % 3 === 0 && i % 5 === 0) {
      console.log('fizzbuzz');
    } else if(i % 3 === 0) {
      console.log('fizz', i);
    } else if(i % 5 === 0) {
      console.log('buzz');
    } else {
      console.log(i);
    }
  }
};


fizzBuzz(15);
fizzBuzz(30);
fizzBuzz(45);
```
