# Two Pointers

The **Two Pointers** algorithm works:
1. Initialize two pointers, usually named "left" and "right", at the beginning and end of the array or string.
2. While the left pointer is less than the right pointer, do the following:
   - a. Move the left pointer to the right, until you find an element that meets a certain condition.
   - b. Move the right pointer to the left, until you find an element that meets a certain condition.
   - c. If the left and right pointers are pointing to elements that meet the same condition, you can perform a certain operation, such as swapping them or calculating their sum.
3. When the left and right pointers meet, you have processed the entire array or string, and can return the result.

The key to the Two Pointers algorithm is that it avoids unnecessary iterations and comparisons by moving both pointers simultaneously.
This results in a faster and more efficient algorithm, especially when dealing with large arrays or strings.

The **time complexity of the Two Pointers algorithm depends on the problem being solved, but in general it is O(n)**,
where n is the length of the input array or string. This is because the algorithm involves iterating over the entire array
or string only once, and each iteration involves moving the left or right pointer by at most one position.

## Example
```JavaScript
// Works only for sorted array
function twoSum(nums, target) {
  let left = 0;
  let right = nums.length - 1;
  
  while (left < right) {
    const sum = nums[left] + nums[right];
    if (sum === target) {
      return [left, right];
    } else if (sum < target) {
      left++;
    } else {
      right--;
    }
  }
  
  return [-1, -1]; // no such pair exists
}

const nums = [2, 7, 11, 15];
const target = 9;
const result = twoSum(nums, target);

console.log(result); // [0, 1] (indices of the pair [2, 7])
```
