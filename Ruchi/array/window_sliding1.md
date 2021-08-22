# Prompt

- Find the average of all contiguous subarrays of size ‘5’ in the given array. Let’s solve this:
- Example: `Array: [1, 3, 2, 6, -1, 4, 1, 8, 2], K=5`
- For the first 5 numbers (subarray from index 0-4), the average is: (1+3+2+6-1)/5 => 2.2(1+3+2+6−1)/5=>2.2
  The average of next 5 numbers (subarray from index 1-5) is: (3+2+6-1+4)/5 => 2.8(3+2+6−1+4)/5=>2.8
  For the next 5 numbers (subarray from index 2-6), the average is: (2+6-1+4+1)/5 => 2.4(2+6−1+4+1)/5=>2.4
  …
- Here is the final output containing the averages of all contiguous subarrays of size 5:
  `Output: [2.2, 2.8, 2.4, 3.6, 2.8]`

#### input / output

input=>array of ints, int
output=>array of average

## Here is the pseudoCode =>

- collect items is the window
- loop till the end where the end point starts from 0
  - keep adding the items in the windowSum
  - check the winodwLength i.e
  - if (end-start)=len-1 (as 0 index)
    - push the avg in result
    - exclude the start element from the window
    - shift the start
- return result

## Here is the code =>

```js
//Array: [1, 3, 2, 6, -1, 4, 1, 8, 2]
//        0   1  2  3  4  5  6
function findAvg(arr, len) {
  let start = 0;
  let result = [];
  let windowSum = 0;
  for (let end = 0; end < arr.length; end++) {
    //end=8
    windowSum += arr[end]; //1,4,6,12,11,14,12,18,14
    if (end - start === len - 1) {
      //end=8,start=4
      result.push(windowSum / len);
      windowSum -= arr[start]; //10,11,10,12,
      start++; //start=1,2,3,4
    }
  }
  return result;
}
```
