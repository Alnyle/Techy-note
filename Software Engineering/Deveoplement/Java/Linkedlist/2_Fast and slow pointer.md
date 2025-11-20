if question contain cycle LinkedList then use this technique

#### #Given `head`, the head of a linked list, determine if the linked list has a cycle in it


slow pointer move one by one while fast point will move two by two until they met at particular point if there a cycle in the LinkedList

```
public class Solution {

    public boolean hasCycle(ListNode head) {
        if (head == null) return false; // check the head is null
        ListNode slow = head;
        ListNode fast = head.next;

        while (slow != null && fast != null && fast.next != null) {

            if (slow == fast) return true;
            
            fast = fast.next.next;
            slow = slow.next;
        }
        return false;
    }
}
```

https://youtu.be/MFOAbpfrJ8g?si=QkK66aw41fXvR83j