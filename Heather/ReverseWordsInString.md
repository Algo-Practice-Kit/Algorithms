# Reverse Words In A String

## Extra Resources

https://www.algoexpert.io/questions/Reverse%20Words%20In%20String

## Prompt

Write a funtion that takes in a string of words separated by one or more whitespaces and returns a string that has these words in reverse order. For example, given the string "tim is great", your function should return "great is tim".

For this problem, a word can contain special characters, punctuation, and numbers. The words in the string will be separated by one or more whitesoaces, and the reversed string must contain the same whitespaces as the original string.

**Note**
You are not allowed to use any built in _split_ or _reverse_ methods/functions. However you are allowed to use a built-in _join_ method/function.

Also note that the input string isn't guaranteed to always contain words.

## Examples

```
string= "Grace Hopper is the best!"
output= "best! the is Grace Hopper"

string= "4    whitespaces"
output="whitespaces    4"
```

### Approaches/Hints

There are several ways to solve this problem, and both require locating the words in the string. How can you find all the words in the string?

Remember that if you find all the words that you also need to keep track of the whitespaces.

Another possible way to approach this problem is to start by reversing the entire string. The you need to reverse each word back.

## Solution

_AlgoExpert has Two solutions posted. This is one:_

```
//helper function
function reverseList(list){
 let start = 0;
 let end = list.length - 1;
 while (start < end){
   const temp= list[start];
   list[start] = list[end];
   list[end] = temp;
   start++;
   end--;
 }
}

function reverseWordsInString(string){
 let words = [];
 let startOfWord = 0;
 for(let idx = 0; idx < string.length; idx++) {
   let character = string[idx];

   if(character = " ") {
     words.push(string.slice(startOfWord, idx));
     startOfWord = idx;
   } else if (string[startOfWord] === " " ){
     words.push(" ");
     startOfWord = idx;
   }
 }
 words.push(string.slice(startOfWord));

 reverseList(words);
 return words.join('');
}

```

_The solution I used:_

```
function reverseWordsInString(string) {
 // Write your code here.
 //ie cat--dog
 let strArr=[];
 let currWord='';
 for(let i= 0; i < string.length; ++i){
   let currLett=string[i];

   if(currLett !== ' ') {
     currWord += currLett;
   }
  else {
    currWord.length && strArr.push(currWord);
    currWord = "";
    strArr.push(currLett)
  }
 }
strArr.push(currWord);

 let reversedStr=[]
 for(let i=string.length - 1; i >=0; i--){
   reversedStr.push(strArr[i])
 }
 return reversedStr.join('')
}
```

## Time and Space Complexity

**Time**
O(n)- have to go through length of string
**Space**
O(n) - have to store copy of string
