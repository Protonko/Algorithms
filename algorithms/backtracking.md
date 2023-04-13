# Backtracking
**Backtracking** is a general algorithmic technique that involves exploring all possible solutions to a problem
by incrementally building candidates and abandoning a candidate as soon as it determines that the candidate cannot possibly
be completed to a valid solution. It is commonly used to solve optimization problems, such as finding the shortest path
or the optimal configuration of a problem.

The main idea of backtracking is to build a solution incrementally, one component at a time, and check at each step
whether the current partial solution can be extended to a complete solution.
If it cannot, we backtrack and try a different option. This process continues until a valid solution is found
or all possible candidates have been explored.

The backtracking algorithm can be implemented recursively, where each recursive call represents a step in the construction of the solution.
1. At each step, we check if the current partial solution satisfies the problem's constraints.
2. If it does, we continue to the next step.
3. If it does not, we backtrack to the previous step and try a different option.

The time complexity of backtracking depends on the size of the problem and the number of solutions to the problem.
In some cases, backtracking can lead to an exponential time complexity, making it impractical for large-scale problems.
However, in some cases, backtracking can be an efficient algorithm for solving complex problems.

## Example:
```javascript
const permute = nums => {
  const res = []
  backtrack(nums, [], res)
  return res
}

const backtrack = (nums, path, res) => {
  if (!nums.length) {
    res.push(path)
    return
  }

  for (let i = 0; i < nums.length; i++) {
    backtrack([...nums.slice(0, i), ...nums.slice(i+1)], [...path, nums[i]], res)
  }
}

console.log(permute([1, 2, 3]))
/**
Result:
[
  [1, 2, 3],
  [1, 3, 2],
  [2, 1, 3],
  [2, 3, 1],
  [3, 1, 2],
  [3, 2, 1]
]
*/
```
