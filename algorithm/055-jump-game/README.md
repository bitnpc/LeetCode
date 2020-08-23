## 55. Jump Game
### Difficulty

 <font color=orange>Medium</font>

### Description

Given an array of non-negative integers, you are initially positioned at the
first index of the array.

Each element in the array represents your maximum jump length at that
position.

Determine if you are able to reach the last index.

**Example 1:**
        
    Input: [2,3,1,1,4]
    Output: true
    ## Explanation: Jump 1 step from index 0 to 1, then 3 steps to the last index.
    

**Example 2:**
        
    Input: [3,2,1,0,4]
    Output: false
    ## Explanation: You will always arrive at index 3 no matter what. Its maximum
                 jump length is 0, which makes it impossible to reach the last index.
    


### Related Topics

Array, Greedy


### Link
[Jump Game](https://leetcode.com/problems/jump-game)


### Solutions
#### Approach 1: Dynamic Programming
倒叙遍历数组，用 `flag` 数组标记可达性，0 表示不可达，1 表示可达，最后数组第一个元素的标记应为 1。  
时间复杂度: `O(n^2)`
空间复杂度: `O(n)`

```
class Solution {
public:
    int min(int a, int b) {
        return a > b ? b : a;
    }
    bool canJump(vector<int>& nums) {
        if (nums.size() <= 1) return true;
        vector<int> flag(nums.size(), 0);
        flag.back() = 1;
        for (int i = nums.size() - 1; i >= 0; i--) {
            int maxIdx = min(i + nums[i], nums.size() - 1);
            for (int j = i + 1; j <= maxIdx; j++) {
                if (flag[j] == 1) {
                    flag[i] = 1;
                    break;
                }
            }
        }
        return flag[0] == 1; 
    }
};
```

#### Approach 2: Dynamic Programming
用 `dp` 数组表示还剩多少步可以走。状态转移方程为 `dp[i] = max(dp[i - 1], nums[i - 1]) - 1`  
时间复杂度: `O(n)`  
空间复杂度: `O(1)`

```
class Solution {
public:
    bool canJump(vector<int>& nums) {
        if (nums.size() <= 1) return true;
        vector<int> dp(nums.size(), 0);
        for (int i = 1; i < nums.size(); i++) {
            dp[i] = max(dp[i - 1], nums[i - 1]) - 1;
            if (dp[i] < 0) {
                return false;
            }
        }
        return true;
    }
};


#### Approach 2: Greedy
贪心策略为: 每次都选最远能够到达的步数  
时间复杂度: `O(n)`  
空间复杂度: `O(1)`
```
class Solution {
public:
    bool canJump(vector<int>& nums) {
        if (nums.size() <= 1) return true;
        int live = 1;
        for (auto n: nums) {
            live--;
            if (live < 0) {
                return false;
            }
            live = max(live, n);
        }
        return true;
    }
};
```
换一种简介的写法
```
class Solution {
public:
    bool canJump(vector<int>& nums) {
        int n = nums.size(), reach = 0;
        for (int i = 0; i < n; ++i) {
            if (i > reach || reach >= n - 1) break;
            reach = max(reach, i + nums[i]);
        }
        return reach >= n - 1;
    }
};
```