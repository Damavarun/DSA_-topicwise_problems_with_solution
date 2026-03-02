# 136. Single Number

🔗 **LeetCode:** https://leetcode.com/problems/single-number/

**Difficulty:** Easy  
**Topic:** Arrays, Hashing  

---

## 🧠 Problem Statement

Given a **non-empty array of integers `nums`**, every element appears **twice except for one**.  
Find that **single one**.

---

## 💡 Approach: Hash Map (Frequency Count)

### Idea
- Use a hash map to store the frequency of each number.
- Traverse the map to find the element with frequency `1`.

---

## 🧾 Algorithm
1. Create an unordered map to store frequency.
2. Traverse the array and increment frequency for each number.
3. Traverse the map:
   - Return the element whose frequency is `1`.

---

## 💻 C++ Code

```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        unordered_map<int, int> mpp;

        for(int i = 0; i < nums.size(); i++) {
            mpp[nums[i]]++;
        }

        for(auto it : mpp) {
            if(it.second == 1) {
                return it.first;
            }
        }
        return -1;
    }
};
