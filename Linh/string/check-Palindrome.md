# Check a string is palindrome
- Determine a string is palindrome ?
- Palindrom => read backward === read forward

# Approachs:
 1. reverse string by create new string, loop backward
 2. reverse an array ...
 3. use two pointers left and right + while loop

# Solution with 2 pointers:

```js
function checkPalindrome(str){
  let left =0;
  let right = str.length-1
  while(left<right){
    if(str[left]!=str[right]) return false
    if(str[left]===str[right]){
      left++
      right--
    }
  }
return true
}

let string ="aabcbcaa"
 let result =checkPalindrome(string)
console.log(result)
```
