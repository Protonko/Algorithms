# Boyer-Moore Voting
The **Boyer-Moore Voting Algorithm** is a algorithm for finding the majority element in an array in **O(n) time and O(1) space complexity**.

The algorithm works by iterating through the array, keeping track of a candidate and a count.

Initially, the candidate is set to the first element of the array, and the count is set to 1.

We then iterate through the rest of the array, updating the candidate and the count based on the current element.

If the current element is the same as the candidate, we increment the count.

If the current element is different from the candidate, we decrement the count.

If the count becomes 0, we reset the candidate to the current element and set the count to 1.

At the end of the iteration, the candidate will be the majority element, if one exists.

## Example:
```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var majorityElement = function(nums) {
    let count = 0
    let candidate

    nums.forEach(num => {
        if (!count) {
            candidate = num
        }

        count = candidate === num ? 1 : -1
    })

    return candidate
};
```


