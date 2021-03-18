## Remove Nth Node From End of List (leetcode.com #19 )

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

Given the head of a linked list, remove the nth node from the end of the list and return its head.

Follow up: Could you do this in one pass?

#####First approach (Time complexity - O(L), 2L- n operations)

1) The n-th element from the end is the element number L - n +1 from the start.
We need to find L - the list length. 
2) We should add at the start the "dummy" element.
3) Find L - the list's length.
4) Find L-n-th element starting from 'dummy'.
5) Change it's ".next" to ".next.next".

```java
class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode pointer = head;
        int length = 0;
        
        while(pointer != null) {
            length++;
            pointer = pointer.next;
        }
        length -= n;
        pointer = dummy;
        while (length > 0) {
            pointer = head.next;
            length--;
        }
        pointer.next = pointer.next.next;

        return dummu.next;     
    }
}
```