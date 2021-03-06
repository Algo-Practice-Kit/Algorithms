# Contains Duplicates 1 (Bonus Follow Up)

---

# Contains Duplicates 1

## Extra Resources

From Leetcode=>
https://leetcode.com/problems/contains-duplicate

## Prompt

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

### Examples

Example 1:

```
Input: nums = [1,2,3,1]
Output: true
```

Example 2:

```
Input: nums = [1,2,3,4]
Output: false
```

Example 3:

```
Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true
```

### Constraints:

1 <= nums.length <= 105
-109 <= nums[i] <= 109

## Solution

```
function containsDuplicate (nums) {
    let key={};
  for(let i=0; i<nums.length; ++i){
      if(key[nums[i]]) return true;
      else key[nums[i]] = true;
  }
    return false;
};
```

## Time and Space Complexity

**Time**
0(n)
-worst case if you have to loop to the last number in the array
**Space**
0(n)
-worst case if you have to store every number in the object

---

# Contains Duplicates 2

## Extra Resources

From Leetcode=>
https://leetcode.com/problems/contains-duplicate-ii/

## Prompt

Given an integer array nums and an integer k, return true if there are two distinct indices i and j in the array such that nums[i] == nums[j] and abs(i - j) <= k.
(So if the same num occurs twice, is the distance between their idices less than <= k?)

### Examples

Example 1:

```
Input: nums = [1,2,3,1], k = 3
Output: true
```

Example 2:

```
Input: nums = [1,0,1,1], k = 1
Output: true

```

Example 3:

```
Input: nums = [1,2,3,1,2,3], k = 2
Output: false

```

### Constraints:

- 1 <= nums.length <= 105
- -109 <= nums[i] <= 109
- 0 <= k <= 105

## Solution

```

```

## Time and Space Complexity

**Time**

**Space**
