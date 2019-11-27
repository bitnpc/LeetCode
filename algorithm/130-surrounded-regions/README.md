## 130. Surrounded Regions
### Difficulty

 <font color=orange>Medium</font>

### Description

Given a 2D board containing `'X'` and `'O'` ( **the letter O** ), capture all
regions surrounded by `'X'`.

A region is captured by flipping all `'O'`s into `'X'`s in that surrounded
region.

**Example:**
        

After running your function, the board should be:
        

## Explanation:

Surrounded regions shouldn't be on the border, which means that any `'O'` on
the border of the board are not flipped to `'X'`. Any `'O'` that is not on the
border and it is not connected to an `'O'` on the border will be flipped to
`'X'`. Two cells are connected if they are adjacent cells connected
horizontally or vertically.


### Related Topics

Depth-first Search, Breadth-first Search, Union Find


### Link
[Surrounded Regions](https://leetcode.com/problems/surrounded-regions)