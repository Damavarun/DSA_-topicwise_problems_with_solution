# 268. Missing Number

🔗 **LeetCode:** https://leetcode.com/problems/missing-number/

**Difficulty:** Easy  
**Topic:** Arrays, Math  

---

## 🧠 Problem Statement

Given an array `nums` containing `n` distinct numbers in the range `[0, n]`,  
return the **only number** in the range that is missing from the array.

---

## ✨ Examples

### Example 1
**Input:**
nums = [3,0,1]

**Output:**
 2 

 
---

## 💡 Optimal Approach: Mathematical Formula (Sum Method)

### Idea

- The numbers are in the range `[0, n]`
- Total count = `n`
- The expected sum of numbers from `0 to n` is:



- Calculate the actual sum of array elements.
- The missing number = **Expected Sum - Actual Sum**

---

## 🧾 Algorithm

1. Let `n = nums.size()`
2. Compute expected sum:
sum = n * (n + 1) / 2

3. Compute actual sum of elements.
4. Return:


---

## 💻 C++ Code (Your Solution)

```cpp
class Solution {
public:
 int missingNumber(vector<int>& nums) {
     int n = nums.size();
     int sum = n * (n + 1) / 2;

     int cnt = 0;
     for(int i = 0; i < n; i++) {
         cnt = cnt + nums[i];
     }

     return sum - cnt;
 }
};
