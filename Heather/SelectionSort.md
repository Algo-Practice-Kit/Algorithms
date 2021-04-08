# Selection Sort

## Extra Resources

https://www.interviewcake.com/concept/java/selection-sort

https://www.tutorialspoint.com/data_structures_algorithms/selection_sort_algorithm.htm

## Prompt

Write a function that takes in an **unsorted** array of integers and returns a sorted version of that array. Use the selection sort array to sort the array. (_Do not use built in array methods to sort the array._)

### Approach/Hint

Consider the input array as two subarrays in place. The first array is sorted at all times and should start with a length of 0, while the second subarray should be unsorted. Find the smallest element in the unsorted subarray and insert it into the sorted subarray with a swap. Repeat this process of finding the smallest until the entire array is sorted.

**Fun fact**- You can now swap in js with a type of destructuring.
example:

```
let a = 1;
let b = 2;

[a, b] = [b, a];

a; // => 2
b; // => 1
```

## Solution

```
function selectionSort(array){
  let start = 0;  //first element/end of sorted arrray

  while (start < array.length -1){
    let smallestIdx = start;

    for(let i= start + 1; i < array.length; ++i){
      if(array[smallestIdx] > array[i]){
        smallestIdx = i;
      }
    }
    [array[smallestIdx], array[start]] = [array[start], array[smallestIdx]]; //that fancy swap
    start++; //move the end of sorted subarray
  }
  return array;
}
```

## Time and Space Complexity

**Time**
0(n^2)
(Because of nested loop)
**Space**
0(1)
(Because you don't create and extra array)
