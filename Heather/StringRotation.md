# String Rotation

## Resources

https://www.pcoroneos.com/cracking-the-code-interview-1-9-string-rotation

(In Java)
Read more: https://www.java67.com/2017/07/string-rotation-in-java-write-program.html#ixzz6rvuAp4nC

## Prompt

Write a program to check if two given strings (string and rotated) are rotations of another.
_For example_
if string = "IndiaUSAEngland" and rotated= "USAEnglandIndia" then your program should return true but if rotated="IndiaEnglandUSA" then it should return false.

## Extra Information

- For the purpose of this program, you can assume that Strings are rotated on the right side, but you should ask this question to your interviewer before jumping into the solution.

## Examples

```
let string= 'IndiaVsAustralia'
let rotated= 'AustraliaVsIndia'
Output: false
```

```
let string= 'IndiaVsEngland'
let rotated= 'EnglandIndiaVs'
Output: true
```

### Approach/Hints

-We know again rotated must be a rotation of string meaning that while the order of the letters can be different they must be in the same sequence (cannot be randomly scrambled).

## Solution

```
function isRotation(string, rotated){




}
```

## Time and Space Complexity

**Time**

**Space**

## Follow Up Questions

(In Java)
There are a couple of variants of this program that many interviewers ask as follow-ups e.g. how do you solve the problem if strings are rotated on the left side, or can you check if two strings are the rotation of another without using String concatenation. You can try solving those versions by yourself, but if you want to look for a solution, you can check it below.
https://javarevisited.blogspot.com/2017/07/2-ways-to-check-if-one-string-is-rotation-of-another-String.html#axzz4mTtTUc4M
