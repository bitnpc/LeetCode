## 138. Copy List with Random Pointer
### Difficulty

 <font color=orange>Medium</font>

### Description

A linked list is given such that each node contains an additional random
pointer which could point to any node in the list or null.

Return a [**deep
copy**](https://en.wikipedia.org/wiki/Object_copying#Deep_copy) of the list.



**Example 1:**

**![](https://discuss.leetcode.com/uploads/files/1470150906153-2yxeznm.png)**
            Input: {"$id":"1","next":{"$id":"2","next":null,"random":{"$ref":"2"},"val":2},"random":{"$ref":"2"},"val":1}        ## Explanation: Node 1's value is 1, both of its next and random pointer points to Node 2.    Node 2's value is 2, its next pointer points to null and its random pointer points to itself.    



**Note:**

  1. You must return the **copy of the given head**  as a reference to the cloned list.


### Related Topics

Hash Table, Linked List


### Link
[Copy List with Random Pointer](https://leetcode.com/problems/copy-list-with-random-pointer)
