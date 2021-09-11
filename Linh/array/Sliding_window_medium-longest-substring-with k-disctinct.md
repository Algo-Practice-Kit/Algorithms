# Longest Substring with maximum K Distinct Characters (medium)
# Prompt:
Given a string, find the length of the longest substring in it with no more than `K` distinct characters.
# Example 1
- input: `string ="araaci"`; `k=2`
- output: 4
- Explanation: the longest substring with no more than `2` distinct characters is `araa`
# Example 2:
- input: `string ="araaci"`; `k=1`
- output: 2
- Explanation: the longest substring with no more than `1` distinct characters is `aa`
# Example 3:
- Input: String="cbbebi", K=3
- Output: 5
- Explanation: The longest substrings with no more than '3' distinct characters are "cbbeb" & "bbebi".
# Example 4:
- Input: String="cbbebi", K=10
- Output: 6
- Explanation: The longest substrings with no more than '10' distinct characters is "cbbebi"

# Approach
- initialize starting point: start=0
- use an object to keep distinct chars: object={}
- initialize max length value: maxLength =0;

- iterate through te input string
   make endwindow start from the starting point `end=0`
    * check if current char is in the distinct object
      -> Not: object[char]=0 // add
      -> Yes: Increate the value of current char in the distinct object
    * Shrink the window if number of distinct characters in the the object > k(given number)

# Solution
- Replit: https://replit.com/@LinhVu020490/Slidingwindow-longest-substring#index.js
```js
function longestSubstring(str,k){
  let start=0;
  let chars={};
  let maxLength=0;
  for(let end=0; end<str.length; end++){
    let char=str[end]
    if(!(char in chars)){
      chars[char]=1
    }else{
      chars[char]+=1
    }
    while (Object.keys(chars).length>k){
    let leftmostChar=str[start]
    chars[leftmostChar] -=1;
    start+=1
    if(chars[leftmostChar]===0){
      delete chars[leftmostChar]
    }
  }
   maxLength=Math.max(maxLength,end-start+1)
  }
  return maxLength
}

console.log(`Length of the longest substring: ${longestSubstring('araaci', 2)}`);

```
