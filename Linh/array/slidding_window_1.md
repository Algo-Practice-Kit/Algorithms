# Prompt

- Find the average of all contiguous subarrays of size ‘5’ in the given array. Let’s solve this:
- Example: `Array: [1, 3, 2, 6, -1, 4, 1, 8, 2], K=5`
- For the first 5 numbers (subarray from index 0-4), the average is: (1+3+2+6-1)/5 => 2.2(1+3+2+6−1)/5=>2.2
  The average of next 5 numbers (subarray from index 1-5) is: (3+2+6-1+4)/5 => 2.8(3+2+6−1+4)/5=>2.8
  For the next 5 numbers (subarray from index 2-6), the average is: (2+6-1+4+1)/5 => 2.4(2+6−1+4+1)/5=>2.4
  …
- Here is the final output containing the averages of all contiguous subarrays of size 5:
  `Output: [2.2, 2.8, 2.4, 3.6, 2.8]`

# Explain
- We are asked to find the average of all contiguous subarrays of size ‘5’ in the given array.
  + For the first 5 numbers (subarray from index 0-4), the average is: `(1+3+2+6−1)/5 => 2.2`
  + For the second 5 numbers (subarray from index 1-5),the average is `(3+2+6−1+4)/5 => 2.8`
  + For the third 5 numbers (subarray from index 1-5),the average is `(2+6−1+4+1)/5 => 2.4`
  + ...
  + Final ouput array `[2.2, 2.8, 2.4, 3.6, 2.8]`

# Brute Force solution
### Aproach
 - Initialize output array =[]
  - Use nested `for loop`
  - Outer loop - iterate the input array
  - Initialize sum =0 inside the outer loop
  - Inner loop - iterate the subarray - with length (K=5)
    to Calculate sum of this subarray
  - Push average into result array
### Solution
  ```js
  function find_averages_of_subarrays(K, arr) {
  const result = [];
  for (let i = 0; i < arr.length - K + 1; i++) {
    // find sum of next 'K' elements
    sum = 0.0;
    for (let j = i; j < i + K; j++) {
      sum += arr[j];
    }
    result.push(sum / K); // calculate average
  }

  return result;
  }
    const result = find_averages_of_subarrays(5, [1, 3, 2, 6, -1, 4, 1, 8, 2]);
    console.log(`Averages of subarrays of size K: ${result}`);
  ```
# Sliding window solution
 ```js
  function find_averages_of_subarrays(K, arr) {
  const result = [];
  let windowSum = 0.0,
    windowStart = 0;
  for (let windowEnd = 0; windowEnd < arr.length; windowEnd++) {
    windowSum += arr[windowEnd]; // add the next element
    // slide the window, we don't need to slide if we've not hit the required window size of 'k'
    if (windowEnd >= K - 1) {
      result.push(windowSum / K); // calculate the average
      windowSum -= arr[windowStart]; // subtract the element going out
      windowStart += 1; // slide the window ahead
    }
  }

  return result;
}


const result = find_averages_of_subarrays(5, [1, 3, 2, 6, -1, 4, 1, 8, 2]);
console.log(`Averages of subarrays of size K: ${result}`);
 ```
