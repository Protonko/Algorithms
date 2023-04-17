# Sliding window
The **sliding window algorithm** is a common technique used to solve problems involving arrays or strings
by efficiently iterating over a portion of the array or string at a time.
This algorithm works by maintaining a sliding window of fixed size over the array or string,and updating the window as we iterate through the data.

The _**time complexity**_ of the sliding window algorithm is _**O(n)**_, the _**space complexity**_ of the algorithm is _**O(1)**_

## Example
```javascript
// Given an array of integers and a window size, find the maximum sum of any contiguous subarray of that size.
const maxSubarraySum = (arr, windowSize) => {
  let maxSum = 0
  let currentSum = 0
  
  // Initialize the current sum with the sum of the first window
  for (let i = 0; i < windowSize; i++) {
    currentSum += arr[i]
  }
  
  // Iterate over the array, updating the current sum and maximum sum
  for (let i = windowSize; i < arr.length; i++) {
    currentSum = currentSum - arr[i - windowSize] + arr[i]
    maxSum = Math.max(maxSum, currentSum)
  }
  
  return maxSum
}

// Example usage
const arr = [1, 24, 2, 10, 2, 3, 1, 0, 20]
const windowSize = 3

console.log(maxSubarraySum(arr, windowSize)); // Output: 36 (corresponding to the subarray [24, 2, 10])
```
