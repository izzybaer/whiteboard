Given a string return true if the string is a palindrome or false if it is not. Palindromes are strings that form the same word reversed. Include spaces and punctuation in determining if the string is a palindrome.

ex:
  palindome('listen') === true 'silent'
  palindrome('abcdefg') === false 'gfedcba'

```javascript
// not accounting for whitespace / punctuation
const palindrome = (str) => {
  let reversed = str.split('').reverse().join('');

  return str === reversed;
}

palindrome('lolol');


// accounting for whitespace and punctuation
const isPunc = (x) => {
    let punc = ";:.,?!-'\"(){}";

    return punc.indexOf(x) === -1 ? false : true;
}
const isWhiteSpace = (x) => {
    return x === ' ' ? true : false;
}

const palindrome = (str) => {

    // create temporary string
    let compressed = '';

    // check every character in the string
    for (var i = 0; i < str.length; i++){
        let letter = str.charAt(i).toLowerCase();
        
        // add whitespace chars and punc to string
        if (isPunc(letter) === false && isWhiteSpace(letter) === false) {
            compressed += letter;
        }
    }
    return compressed === [...compressed].reverse().join('');
}

console.log(palindrome('A man, a plan, a canal, Panama!  lalala'))

```
