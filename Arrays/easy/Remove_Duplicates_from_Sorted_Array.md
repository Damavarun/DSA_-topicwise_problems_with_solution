# Remove Duplicates from Sorted Array

🔗 LeetCode: https://leetcode.com/problems/remove-duplicates-from-sorted-array/

**Difficulty:** Easy  
**Topic:** Arrays  

---

## 🧠 Problem Statement
Given a sorted array `nums`, remove the duplicates **in-place** such that each unique element appears only once.  
Return the number of unique elements `k`, and modify the array so that the first `k` elements contain the unique values.

---

## 💡 Approach
1. Use a `set` to store all unique elements from the array.
2. Since a set stores elements in sorted order, duplicates are automatically removed.
3. Copy the elements from the set back into the original array.
4. Return the count of unique elements.

---

## ⏱️ Time and Space Complexity
- **Time Complexity:** O(n log n)  
  (Insertion into a set takes `log n` time for each element)
- **Space Complexity:** O(n)  
  (Extra space used by the set)

---

## 💻 Code (C++)

```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        set<int> s;
        
        for(int i = 0; i < nums.size(); i++) {
            s.insert(nums[i]);
        }

        int j = 0;
        for(auto it : s) {
            nums[j++] = it;
        }

        return j;
    }
};