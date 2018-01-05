fibonacci series recursive

the fibonacci series is an ordering of numbers where each number is the sum of the preceeding two.

print out the nth entry in the fibonacci series, recursive

ex: [0, 1, 1, 2, 3, 5, 8, 13, 21, 34] forms the first ten entries of the fibonacci series

ex: fib(4) === 3

why NOT to use recursion to solve fibonacci...
because of runtime complexity. It takes way more time / space to solve this problem recursively than iteratively.

```javascript
const fib = (n) => n < 2 ? n : fib(n - 1) + fib(n - 2);

// fib(0) // prints 0
fib(1) // prints 1

// fib(3) // prints 2
// fib(7) // prints 13
// fib(12) // prints 144
// fib(15) // prints 610
// fib(18) // prints 2584
// fib(21) // prints 10946
```
