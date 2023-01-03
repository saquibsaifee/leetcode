Type: [[Linked List Question (C)]]

Leet code Link: https://leetcode.com/problems/merge-two-sorted-lists/description/

Easy(01/03/2023)

Notes: make new linked list, compare value and keep adding them.

# 21. Merge Two Sorted Lists

You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists in a one **sorted** list. The list should be made by splicing together the nodes of the first two lists.
Return _the head of the merged linked list_.

**Example 1:**

![](https://assets.leetcode.com/uploads/2020/10/03/merge_ex1.jpg)

**Input:** list1 = [1,2,4], list2 = [1,3,4]
**Output:** [1,1,2,3,4,4]

**Example 2:**
**Input:** list1 = [], list2 = []
**Output:** []

**Example 3:**
**Input:** list1 = [], list2 = [0]
**Output:** [0]

# Solution:

```python
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        newList = ListNode()
        tail = newList

        while list1 and list2:
            if list1.val < list2.val:
                tail.next = list1
                list1 = list1.next
            else:
                tail.next = list2
                list2 = list2.next
            tail = tail.next

        if list1: tail.next = list1
        elif list2: tail.next = list2

        return newList.next
```