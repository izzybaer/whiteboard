a sentence S is given, each word has upper and lowercase letters
- convert to goat latin
- if a word begins with a vowel(a, e, i, o , u) append "ma" to end of word
- if a word begins with a consonant (not a vowel) remove the first letter and append it to the end, and then add "ma" to the end of word
// "goat" becomes "oatgma"
- add one letter 'a' to the end of each word per its word index in the sentence, starting with 1
    - the first word gets 'a' added to the end, the second word gets 'aa' added to the end, the third word gets 'aaa' added to the end
- return the final sentence representing the conversion from S to Goat Latin

```js
const goatLatin = (str) => {
    let array = str.split(' ');
    console.log(array)
    let vowels = { 'a': true, 'e': true, 'i': true, 'o': true, 'u': true };

    for (var i = 0; i < array.length; i++){
        let word = array[i].split(' ');

        if (!vowels[word[0].toLowerCase()]) {
            word.push(word.shift());
        }
        word.push('ma');

        for (var j = i + 1; j; j--){
            word.push('a');
        }
        console.log(word)
    }
    return array.join(' ');
}
let tes = 'my name is Izzy and I love goats'
console.log(goatLatin(tes));
```