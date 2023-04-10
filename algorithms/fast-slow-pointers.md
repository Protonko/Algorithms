# Fast-Slow Pointers

The **fast-slow pointers** algorithm  uses two pointers
that move through the array or linked list at different speeds.
The "slow" pointer moves one element at a time, while the "fast" pointer moves two elements at a time.
This creates a gap between the two pointers that increases with each iteration.

The basic idea behind the algorithm is to use the gap between the two pointers to detect some property of the array or linked list.
For example, if the array is sorted, we can use the pointers to find a target element by comparing the values at the pointers
and adjusting their positions accordingly.
Similarly, if the linked list has a cycle, we can use the pointers to detect the cycle by checkingif the fast pointer ever catches up to the slow pointer.

![Slow-fast Pointers description](https://github.com/Protonko/Algorithms/blob/master/images/Slow-Fast-Ponters-1.png)

## Example
```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} head
 * @return {boolean}
 */
var hasCycle = function(head) {
    let slow = head
    let fast = head

    while (fast?.next?.next) {
        fast = fast.next.next
        slow = slow.next

        if (slow === fast) {
            return true
        }
    }

    return false
};
```
