# Check if Array Is Sorted and Rotated

🔗 LeetCode: https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/

**Difficulty:** Easy  
**Topic:** Arrays  

---

## 🧠 Problem Statement
Given an array `nums`, determine whether it was originally sorted in non-decreasing order and then rotated some number of times (including zero rotations).  
Duplicates are allowed.

---

## 💡 Approach
- Traverse the array and compare each element with the next element.
- If the array is sorted and rotated, there can be **at most one index** where  
  `nums[i] > nums[i + 1]`.
- Use modulo (`%`) to compare the last element with the first, handling rotation.
- If such a condition occurs more than once, the array is not sorted and rotated.

---

## ⏱️ Time and Space Complexity
- **Time Complexity:** O(n)  
- **Space Complexity:** O(1)

---

## 💻 Code (C++)

```cpp
class Solution {
public:
    bool check(vector<int>& nums) {
        int count_rotate = 0;
        int n = nums.size();

        for(int i = 0; i < n; i++) {
            if(nums[i] > nums[(i + 1) % n]) {
                count_rotate++;
            }
            if(count_rotate > 1) {
                return false;
            }
        }
        return true;
    }
};