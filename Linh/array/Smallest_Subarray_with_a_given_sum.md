# Smallest Subarray with a given sum (easy)

### Prompt:

Given an array of positive numbers and a positive number `S`, find the LENGTH of the smallest contiguous subarray whose sum is greater than or equal to `S`. Return 0 if no such subarray exist.

### Example 1

- Input: `[2,1,5,2,3,2]`; `S=7`
- Ouput: `2`
- Explanation: The smallest subarray with a sum greater or wqual to `7` is [5,2]

### Example 2

- Input: `[2,1,5,2,8`, `S=7`
- Output: `1`
- Explaination: The smallest subarray with a sum greater than or equal to `7` is `[8]`

### Example 3:

- Input: `3,4,1,1,6`; `S=8`
- Ouput: `3`
- Explaination: Smallest subarrays with a sum greater than or equal to `8` are `[3,4,1]`

### Apporach

- initialize windowStart=0
- initialize calculation value: windownSum =0
- initialize value to keep track: minLength = Infinity
- use 1 `for loop` to increase index `endWindow`
- inside the `for loop`;
- calculate `windowSum`
- compare `windowSum` vs given sum `S`
- while `windowSum`>= `S`
  - compare `minLength` vs current length of subarray => get new `minLength`
  - shrink size of subarray by keep removing the `windowStart`: `windowSum -=input[windowStart]` and `windowStart++`

### Solution:

```js
 funtion smallest_length_of_subarray(array,S){
   let windowStart =0;
   let windowSum =0;
   let minLength = Infinity;
   for(let windowEnd =0; windowEnd < array.length; windowEnd++){
     windowSum+=array[windowEnd];
     while(windowSum>=S){
       currentLength = windowEnd - windowStart +1;
       minLength = Math.min(minLength,currentLength);
       windowSum -=array[windowStart]
       windowStart +=1
     }
   }
   if(minLength === Infinity){
     minLength =0
   }
   return minLength;
 }
```
