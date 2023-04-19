# Dynamic programming
**Dynamic programming** is an algorithmic technique that solves complex problems by breaking them down into smaller subproblems and storing the solutions of those subproblems to avoid redundant computation.
There are two main approaches to dynamic programming: _bottom-up_ and _top-down_.

_**Bottom-up dynamic programming**_ involves solving the subproblems in a sequence, starting with the smallest subproblems and working up to the largest.
Each subproblem's solution is stored in an array or table, and the solution to larger subproblems is computed using the solutions to smaller subproblems.

## Example of bottom-up dynamic programming to find the nth Fibonacci number:
```javascript
const fibonacci = n => {
  const fib = [0, 1] // Initialize the first two Fibonacci numbers
  for (let i = 2; i <= n; i++) {
    fib[i] = fib[i-1] + fib[i-2] // Compute the ith Fibonacci number
  }
  return fib[n] // Return the nth Fibonacci number
}

console.log(fibonacci(6)) // Output: 8
```

In this example, we use a loop to compute each Fibonacci number up to the nth number.
The solutions to smaller subproblems (the (i-1)th and (i-2)th Fibonacci numbers)
are stored in the fib array, and the solution to each larger subproblem (the ith Fibonacci number)
is computed using the solutions to the smaller subproblems.

_**Top-down dynamic programming**_, also known as memoization, involves recursively solving the subproblems and storing the solutions
in a memoization table to avoid redundant computation.
When a subproblem is encountered again, its solution is retrieved from the memoization table instead of recomputing it.

## Example of top-down dynamic programming to find the nth Fibonacci number:
```javascript
const fibonacci = (n, memo = {}) => {
  if (n in memo) return memo[n]; // Return the memoized solution if it exists
  if (n <= 1) return n; // Base case
  memo[n] = fibonacci(n - 1, memo) + fibonacci(n - 2, memo); // Compute and memoize the solution
  return memo[n]; // Return the computed solution
}

console.log(fibonacci(6)); // Output: 8
```

In this example, we use recursion to compute each Fibonacci number up to the nth number,
but we store the solutions in the memo object to avoid recomputing them. When a subproblem is encountered again,
its solution is retrieved from the memo object instead of computing it again.

