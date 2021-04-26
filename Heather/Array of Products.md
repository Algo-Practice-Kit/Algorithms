# Array of Products

## Extra Resources

https://www.algoexpert.io/questions/Array%20Of%20Products

## Prompt

Write a function that takes in a non-empty array of integers and returns an array of the same length, where each element in the output array is equal to the product of every other number in the input array.

In other words, the value at output[i] is equal to the product of every number in the input array other than input[i].

Note you are expected to solve this problem without using division.

### Examples

```
input array=[5, 1, 4, 2]
output array=[8, 40, 10, 20]
```

### Constraints:

-Minimum length of array is 2
-Not necessarily sorted
-Can have positive and negative values

## Solution

_With pointers_
To make a right and a left array with the products of all items to the left and right of (and exclusive of) the current item's position.

```
function arrayOfProducts(array) {
  // Write your code here.
	// [5, 1, 4, 2]
let leftProducts=Array(array.length).fill(1);
	let rightProducts=Array(array.length).fill(1);
let productArr=[];
	//fill left the loop
	let leftCurr = 1;
	for(let i=0; i < array.length; ++i){
		leftProducts[i]=leftCurr;
		leftCurr *=array[i]

	}
		//fill right the loop
	let rightCurr = 1;
	for(let i=array.length -1; i >=0; --i){
		rightProducts[i]=rightCurr;
		rightCurr *=array[i]

	}
	//multiply correct indexes together
for(let i=0; i <array.length; ++i){
	productArr[i]= leftProducts[i] * rightProducts[i];
}
	console.log(rightProducts, leftProducts)
	return productArr;
}


```

## Time and Space Complexity

**Time**

**Space**
