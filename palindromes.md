Given a string return true if the string is a palindrome or false if it is not. Palindromes are strings that form the same word reversed. Include spaces and punctuation in determining if the string is a palindrome.

ex:
  palindome('listen') === true 'silent'
  palindrome('abcdefg') === false 'gfedcba'

```javascript
const palindrome = (str) => {
  let reversed = str.split('').reverse().join('');

  return str === reversed;
}

palindrome('lolol')
```
