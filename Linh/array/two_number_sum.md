# TWO NUMBER SUM
## Prompt
Write a function that takes in a non empty array of distinct integers and an integer representing a target sum. If any two numbers in the input array sumup to the target sum, the function should return them in an array, in any order.
If no TWO NUMBERS that sumup to the target sum, the function should return an empty array.

Note that the target sum has to be obtained by summing two different integers in the array; you can't add a single integer to itself in order to obtain the target sum.
You can assume that there will be at most one pair of numbers summing up to the target sum

## Example:
- input: `array = [3,5,-4,8,11,1,-1,6]` ; targetSum =`10`;
- output: `[-1, 11]`

## Clarify questions and Edge cases
notes:
- ask questions! there are many approaches to this prompt. definitely ask whether or not the array is mutable
- ** this question usually has, at most, one pair **
- all distinct numbers, no repeating numbers
- pairs will be distinct numbers as well
- can i sort/mutate the input array?
- be proactive by asking questions!!!!
- ** forgot to ask the edge case where no pairs can be found **
-

## Approach
### Case 1: you can mutate input array

#### Approach 1: Sort array; Using While loop and 2 pointers -left & right
- sorting the array
- using two pointers to iterate through the input array...
  - first pointer will be first index
  - second pointer will be the end
#### Solution 1:

```js
const twoNumberSum2 = (array, targetSum) => {
	array.sort((a, b) => a - b)
	let left = 0
	let right = array.length - 1
	while (left < right) {
		const currentSum = array[left] + array[right];
		if (currentSum === targetSum) {
			return [array[left], array[right]]
		} else if (currentSum < targetSum) {
			left++
		} else if (currentSum > targetSum) {
			right--
		}
	}
	return []
}
```
### Case 2: you can not mutate input array

#### Solution 1: Use nested loop
```js
const twoNumberSum1 = (array, targetSum) => {
	for (let i = 0; i < array.length - 1; i++) {
		let firstNum = array[i]
		for (let j = i + 1; j < array.length; j++) {
			let secondNum = array[j]
			if (firstNum + secondNum === targetSum) {
				return [firstNum, secondNum]
			}
		}
	}
	return []
}
```
#### Solution 2: Use object /hash table to store remainder
```js
function twoNumberSum3(array, targetSum) {
	let remainderColection = {}
	for (const num of array) {
		let potentialMatch = targetSum - num
		if (remainderColection.hasOwnProperty(potentialMatch)) {
			//(potentialMatch in remainderColection)
			return [potentialMatch, num]
		} else {
			remainderColection[num] = true
		}
	}

	return []
}
```

