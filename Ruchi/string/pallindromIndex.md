```js
function palindromeIndex(s) {
  let left = 0;
  let right = s.length - 1;
  while (left < right) {
    if (s[left] !== s[right]) {
      //if it's not a palindrome
      console.log("not a palindrome");
      //first take off the left char and
      //check for palindrome for the rest of the string
      //if it's a palindrome return left
      let newStr = s.substring(left + 1, right + 1);
      console.log(newStr);
      if (palindromeIndex(newStr) === -1) {
        console.log("rest is palindrome after excluding the left");
        return left;
      }
      //else take off the right and check the rest for palindrome and
      //then return right

      if (palindromeIndex(s.substring(left, right) === -1)) {
        return right;
      }
    }
    left++;
    right--;
  }
  return -1;
}

palindromeIndex("bcbc");
//palindromeIndex("abcdefghihgfeddcba");
```
