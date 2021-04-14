# String Rotation

### Resources

https://www.pcoroneos.com/cracking-the-code-interview-1-9-string-rotation

(In Java)
Read more: https://www.java67.com/2017/07/string-rotation-in-java-write-program.html#ixzz6rvuAp4nC

## Prompt

Write a function to check if two given strings (str and rotatedStr) are rotations of another.
_For example_
if str = "IndiaUSAEngland" and rotatedStr= "USAEnglandIndia" then your program should return true but if rotatedStr="IndiaEnglandUSA" then it should return false.

### Examples

```
let str= 'IndiaVsAustralia'
let rotatedStr= 'AustraliaVsIndia'
Output: false
```

```
let str= 'IndiaVsEngland'
let rotatedStr= 'VsEnglandIndia
Output: true
```

## Approach/Hints

- While the order of the letters can be different they must be in the same sequence (cannot be randomly scrambled).

- You are allowed to use .includes()!

- For the purpose of this function, you can assume that strings are rotated to the right side, but you should ask this question to your interviewer before jumping into the solution.

## Solution

I like this question because it's a good example of thinking out of the box. Because the answer is a _boolean, you can use includes, AND don't need to keep track of indices_, the simplest solution is to concat the string to itself. Then check if the rotated string is within that string.

```
// function isRotation(string, rotated){
// let compare= string + string;
// if(compare.includes(rotated)) return true;
// return false;
// };
```

## Time and Space Complexity

I couldn't find the BigO but I assume...
**Time**
O(n) because includes is searching the string behind the scenes
**Space**
O(n) because you are doubling and storing the sting length

### Follow Up Questions

(In Java)
There are a couple of variants of this program that many interviewers ask as follow-ups e.g. how do you solve the problem if strings are rotated on the left side, or can you check if two strings are the rotation of another without using String concatenation. You can try solving those versions by yourself, but if you want to look for a solution, you can check it below.
https://javarevisited.blogspot.com/2017/07/2-ways-to-check-if-one-string-is-rotation-of-another-String.html#axzz4mTtTUc4M
