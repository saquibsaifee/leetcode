[[Linked List Question (C)]]
Easy (12/04/2022)
Leet code link: https://leetcode.com/problems/middle-of-the-linked-list/description/
Notes: Iterate the linked list and store the length. return len//2

# 876. Middle of the Linked List

Given the `head` of a singly linked list, return _the middle node of the linked list_.

If there are two middle nodes, return **the second middle** node.

**Example 1:**

![](https://assets.leetcode.com/uploads/2021/07/23/lc-midlist1.jpg)

**Input:** head = [1,2,3,4,5]
**Output:** [3,4,5]
**Explanation:** The middle node of the list is node 3.

**Example 2:**

![](https://assets.leetcode.com/uploads/2021/07/23/lc-midlist2.jpg)

**Input:** head = [1,2,3,4,5,6]
**Output:** [4,5,6]
**Explanation:** Since the list has two middle nodes with values 3 and 4, we return the second one.


# Solution 1
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if not head: return head

        i,curr = 0, head

        while curr:
            i,curr = i+1, curr.next

        mid,i,curr = i // 2, 0, head

        while curr:
            if i == mid: return curr
            i, curr = i+1, curr.next




