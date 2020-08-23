## 45. Jump Game II
### Difficulty

 <font color=red>Hard</font>

### Description

Given an array of non-negative integers, you are initially positioned at the
first index of the array.

Each element in the array represents your maximum jump length at that
position.

Your goal is to reach the last index in the minimum number of jumps.

**Example:**
        
    Input: [2,3,1,1,4]
    Output: 2
    ## Explanation: The minimum number of jumps to reach the last index is 2.
        Jump 1 step from index 0 to 1, then 3 steps to the last index.

**Note:**

You can assume that you can always reach the last index.


### Related Topics

Array, Greedy


### Link
[Jump Game II](https://leetcode.com/problems/jump-game-ii)

### Solutions
#### Approach 1: Dynamic Programming[Time Limit Exceeded]
用 `steps` 数组表示到达当前位置需要的最少步数，遍历数组的时候，不断更新 `steps` 数组对应位置需要的步数  
时间复杂度`O(n^2)`  
空间复杂度`O(n)`  
```
class Solution {
public:
    int min(int a, int b) {
        return a > b ? b : a;
    }
    int jump(vector<int>& nums) {
        if (nums.size() <= 1) return 0;
        vector<int> steps(nums.size(), INT_MAX);
        steps[0] = 0;
        for (int i = 0; i < nums.size(); i++) {
            int maxIdx = min(nums[i] + i, nums.size() - 1);
            for (int j = i + 1; j <= maxIdx; j++) {
                steps[j] = min(steps[j], steps[i] + 1);
            }
        }
        return steps.back();
    }
};
```

#### Approach 2: Greedy
其实是基于`Approach 1`方法的改进，在 `i + nums[i]` 的范围不需要每次都遍历 `num[i]`  
`cur` 记录当前能到达的最远距离，`last` 标记上一跳能到达的最远距离。当 `i` 超过 `last` 时，需要更新 `last`  
时间复杂度`O(n)`  
空间复杂度`O(1)`  
```
class Solution {
public:
    int jump(vector<int>& nums) {
        int res = 0, cur = 0, last = 0;
        for (int i = 0; i < nums.size(); i++) {
            if (i > last) {
                last = cur;
                res++;
            }
            cur = max(cur, i + nums[i]);
        }
        return res;
    }
};
```