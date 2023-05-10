# In-place reversal of a linked list

To perform an **in-place reversal of a linked list**, you need to modify the pointers within the nodes of the list without creating a new list.
The basic idea is to traverse the list from the head to the tail, updating the next pointers of each node to reverse the direction of the list.

## A step-by-step algorithm to reverse a linked list in-place:

1. Initialize three pointers: previous as None, current as the head of the list, and next as None.

2. Traverse the list using the current pointer until it reaches the end of the list (i.e., current becomes None).

- Inside the loop, perform the following operations:

  - a. Save the reference to the next node: next = current.next.

  - b. Update the next pointer of the current node to point to the previous node: current.next = previous.

  - c. Move the previous pointer to the current node: previous = current.

  - d. Move the current pointer to the next node: current = next.

3. After the traversal is complete, the previous pointer will be pointing to the new head of the reversed list.

4. Return the new head of the reversed list.

The **time complexity is O(n)**, and the **space complexity is O(1)**

## Example
```javascript
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var reverseList = function(head) {
    let prev = null
    let curr = head

    while (curr) {
        const next = curr.next
        curr.next = prev
        prev = curr
        curr = next
    }

    return prev
};
```
