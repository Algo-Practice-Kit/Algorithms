# Maximum Nesting Depth Of the Parenthese

## Promt:
- Given a VPS represented as string s, return the nesting depth of s.
- Source: Leetcode: 1614. Maximum Nesting Depth of the Parentheses
- link: https://leetcode.com/problems/maximum-nesting-depth-of-the-parentheses/

## Example
1. Example 1:
- Input: s = "(1+(2*3)+((8)/4))+1"
- Output: 3
- Explanation: Digit 8 is inside of 3 nested parentheses in the string.

2. Example 2:
- Input: s = "(1)+((2))+(((3)))"
- Output: 3

3. Example 3:
- Input: s = "1+(2*3)/(2-1)"
- Output: 1

4. Example 4:
- Input: s = "1"
- Output: 0

## Approach and Solution
### Approach:
- Initialize the `maxDepth =0`
- Initialize the `currentDepth =0`
- Iterate the input string with a for loop
  - Keep track of the current Depth
    - meet a `open bracket` => increase `currentDepth` by 1
    - meet a `close bracket` => decrease `currentDepth` by 1
- Finish looping => return maxDepth

### Solution:
```js
function depth(str){
  let open= '(';
  let closed=')';
  let maxDepth =0
  let currDepth=0
  for(let i=0; i< str.length; ++i){
    let char= str[i];
    if(char=== open){
      currDepth++;
    } else if(char=== closed) {
      maxDepth= Math.max(currDepth, maxDepth)
      currDepth--;

    }

  }

  return maxDepth;
}

let s2= "(1+(2*3)+((8)/4))+1"
let result = depth(s2)
console.log(result)
```
