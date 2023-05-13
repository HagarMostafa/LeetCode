>## Remove Nth Node From End of List
>```
>Given the head of a linked list, remove the nth node from the end of the list and return its head.
>``` 
>### Example 1:
>![image](https://github.com/HagarMostafa/LeetCode/assets/24817937/3d83e770-a2ef-4561-b820-38b13d6a9877)
>```
>Input: head = [1,2,3,4,5], n = 2
>Output: [1,2,3,5]
>```
>### Example 2:
>```
>Input: head = [1], n = 1
>Output: []
>```
>### Example 3:
>```
>Input: head = [1,2], n = 1
>Output: [1]
>```
>### Solution `Java`
```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {
        
        ListNode ptr = head;
        int count = 0;
        while (ptr != null) {
            count++;
            ptr = ptr.next;
        }
        
        if (count == n) {
            head = head.next;
            return head;
        }

        ptr = head;
        n = count - n - 1;
        count = 0;
        
        while (ptr != null) {
            if (count == n) {
                ptr.next = ptr.next.next;
            }
            count++;
            ptr = ptr.next;
        }
        
        return head;
    }
}
```
