
##Merge two sorted LinkedList
### Approach

make two pointer and compare the value of the two nodes and take the node with smallest value and and make move forward 

Time complexity : O(n + m)
n: list1 length
m: list2 length

```
class Solution {

    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        ListNode dummyHead = new ListNode();
        ListNode tail = dummyHead;

        while (list1 != null && list2 != null) {
            if (list1.val <= list2.val) {

                tail.next = list1;

                list1 = list1.next;

                tail = tail.next;

            } else {

                tail.next = list2;

                list2 = list2.next;

                tail = tail.next;
            }

        }
        tail.next = (list1 != null) ? list1 : list2;
        return dummyHead.next;

    }

}

```
``

