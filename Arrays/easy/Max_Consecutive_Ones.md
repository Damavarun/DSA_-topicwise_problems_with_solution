# 485. Max Consecutive Ones

🔗 **LeetCode:** https://leetcode.com/problems/max-consecutive-ones/

**Difficulty:** Easy  
**Topic:** Arrays  

---

## 🧠 Problem Statement

Given a binary array `nums`, return the **maximum number of consecutive `1`s** in the array.

---

## 💡 Optimal Approach (Single Pass)

### Idea
- Traverse the array once.
- Maintain a counter for current consecutive `1`s.
- Reset the counter when `0` is encountered.
- Track the maximum count during traversal.

---

## 🧾 Algorithm
1. Initialize two variables:
   - `cnt = 0` (current consecutive ones)
   - `maxcnt = 0` (maximum consecutive ones)
2. Loop through the array:
   - If `nums[i] == 1`, increment `cnt`
   - Update `maxcnt`
   - If `nums[i] == 0`, reset `cnt = 0`
3. Return `maxcnt`

---

## 💻 C++ Code (Optimal)

```cpp
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int cnt = 0;
        int maxcnt = 0;

        for(int i = 0; i < nums.size(); i++) {
            if(nums[i] == 1) {
                cnt++;
                maxcnt = max(maxcnt, cnt);
            } else {
                cnt = 0;
            }
        }
        return maxcnt;
    }
};
