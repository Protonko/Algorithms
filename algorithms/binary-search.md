# Binary Search

The **Binary Search** algorithm works by repeatedly dividing the search space in half until the target element is found or determined to be absent.

Here's how the **Binary Search** algorithm works:
1. Start with the entire sorted array and define two pointers: _left_ and _right_.
   Set `left` to the first index of the array and `right` to the last index.
2. Calculate the middle index `mid` by finding the average of `left` and `right`.
3. Compare the element at index _mid_ with the target element:
   - If the element at `mid` is equal to the target, the search is successful, and the algorithm returns the index `mid`.
   - If the element at `mid` is less than the target, the target must be in the right half of the array.
     Update `left = mid + 1` to search in the right half.
   - If the element at `mid` is greater than the target, the target must be in the left half of the array.
     Update `right = mid - 1` to search in the left half.
4. Repeat steps 2 and 3 until the target element is found or until left becomes greater than right,
   indicating that the target is not present in the array.
5. If the target element is found, return the index. Otherwise, return -1 to indicate that the target is not present in the array.

**Binary search** has the _time complexity of O(log n)_ and the _space complexity of binary search is O(1)_

## Example
### Iterative Binary Search
```javascript
const binarySearch = (arr, target) => {
  let left = 0
  let right = arr.length - 1

  while (left <= right) {
    let mid = left + Math.floor((right - left) / 2)

    if (arr[mid] === target) {
      return mid
    } else if (arr[mid] < target) {
      left = mid + 1
    } else {
      right = mid - 1
    }
  }

  return -1; // Target not found
}

// Example usage:
const sortedArray = [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
const targetElement = 12

const resultIndex = binarySearch(sortedArray, targetElement) // 5
```

### Recursive Binary Search
```javascript
const binarySearch = (arr, target, left = 0, right = arr.length) => {
  if (left > right) {
    return -1
  }

  const mid = Math.floor((left + right) / 2)

  if (arr[mid] === target) {
    return mid
  } else if (arr[mid] < target) {
    return binarySearch(arr, target, mid + 1, right)
  } else {
    return binarySearch(arr, target, left, mid - 1)
  }
}

// Example usage:
const sortedArray = [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
const targetElement = 12

const resultIndex = binarySearch(sortedArray, targetElement) // 5
```
