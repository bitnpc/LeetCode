## 173. Binary Search Tree Iterator
### Difficulty

 <font color=orange>Medium</font>

### Description

Implement an iterator over a binary search tree (BST). Your iterator will be
initialized with the root node of a BST.

Calling `next()` will return the next smallest number in the BST.



**Example:**

**![](https://assets.leetcode.com/uploads/2018/12/25/bst-tree.png)**
            BSTIterator iterator = new BSTIterator(root);    iterator.next();    // return 3    iterator.next();    // return 7    iterator.hasNext(); // return true    iterator.next();    // return 9    iterator.hasNext(); // return true    iterator.next();    // return 15    iterator.hasNext(); // return true    iterator.next();    // return 20    iterator.hasNext(); // return false    



**Note:**

  * `next()` and `hasNext()` should run in average O(1) time and uses O( _h_ ) memory, where _h_ is the height of the tree.
  * You may assume that `next()` call will always be valid, that is, there will be at least a next smallest number in the BST when `next()` is called.


### Related Topics

Stack, Tree, Design


### Link
[Binary Search Tree Iterator](https://leetcode.com/problems/binary-search-tree-iterator)
