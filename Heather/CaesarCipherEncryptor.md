# Caesar Cipher Encryptor

## Prompt

Given a non-empty string of lowercase letters and a non-negative integer representing a key, write a function that returns a new string obtained by shifting every letter in the input string by k positions in the alphabet, where k is the key.

Note that the letters should 'wrap' around the alphabet; in other words, the letter _z_ shifted by one returns the letter _a_.

## Extra Resources

Unicode
https://developer.mozilla.org/en-US/docs/Glossary/Unicode

### Hints

## 1

Most languages have built in functions thaat give you the Unicode value of a character as well as the character corresponding to a Unicode value. Consider using such functions to determine which letters the input string's letters should be mapped to.

## 2

Try creating your own mapping of letters to codes. In other words, try associating each letter in the alphabet with a specific number - it's position in the alphabet, for instance - and using that to determine which letters the input string's letters should be mapped to.

## 3

How do you handle cases where a letter gets shifted to a position that requires wrapping around the alphabet? What about cases where the key is very large and causes multiple wrapping around the alphabet? The modulo operator should be your friend here.

## Solution 1

Making alphabet key

```
function caesarCipherEncryptor(string, key){
  let alph="abcdefghijklmnopqrstuvwxyz";
  let dict={};
  let newString="";

  //create alphabet key
  for(let i = 0; i < alph.length; ++i){
    dict[i + 1] = alph[i];
    dict[alph[i]] = i + 1;
  }

  for(let j=0; j < string.length; ++j){
    let letterIdx = dict[string[j]] + key;

    if(letterIdx > 26) letterIdx = letterIdx % 26;

    newString += dict[letterIdx];
  }
return newString;
};

```

## Solution 2

Using Unicode

```
function caesarCipherEncryptor(string, key){
 let newKey= key % 26; //for edge case of large key

 let newString= "";

 for(let i = 0; i < string.length; ++i){
   let newLetterValue= string.charCodeAt(i) + newKey;

   if(newLetterValue > 122){
     newString += String.fromCharCode(96 + (newLetterValue % 122))
   } else {
     newString += String.fromCharCode(newLetterValue);
   }
 }


return newString;
};
```

## Time and Space Complexity

n length of the imput string
**Time**
0(n)

**Space**
0(n)
