>## Middle of the Linked List
>```
>Given the head of a singly linked list, return the middle node of the linked list.
>If there are two middle nodes, return the second middle node.
>```
>### Example 1:
>![image](https://github.com/HagarMostafa/LeetCode/assets/24817937/a709470c-232c-4f8e-8347-8feed6c1e11b)
>```
>Input: head = [1,2,3,4,5]
>Output: [3,4,5]
>Explanation: The middle node of the list is node 3.
>```
>### Example 2:
>![image](https://github.com/HagarMostafa/LeetCode/assets/24817937/c8087e57-8934-4c4b-8c04-7b84f5cf8df2)
>```
>Input: head = [1,2,3,4,5,6]
>Output: [4,5,6]
>Explanation: Since the list has two middle nodes with values 3 and 4, we return the second one.
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
    public ListNode middleNode(ListNode head) {
        ListNode p1 = head, p2 = head;
        while (p2 != null && p2.next != null) {
            p1 = p1.next;
            p2 = p2.next.next;
        }
        return p1;
    }
}
```
