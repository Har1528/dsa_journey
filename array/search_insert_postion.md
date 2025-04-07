# 🔍 Search Insert Position

**LeetCode Link**: [Problem #35] ( https://leetcode.com/problems/search-insert-position/ )  
**Difficulty**: Easy  
**Category**: Binary Search  
**Status**: ✅ Solved  
**Language**: C++

---

## 🧠 Problem Statement

Given a **sorted array** of distinct integers and a target value, return the index if the target is found. If not, return the index where it **would be inserted** in order.

You must write an algorithm with **O(log n)** runtime complexity.

---

## 🧾 Examples

**Example 1**:
Input: nums = [1,3,5,6], target = 5
Output: 2


**Example 2**:
Input: nums = [1,3,5,6], target = 2
Output: 1

## 💡 Approach

This is a classic **binary search** problem.  
If the element is not found, the left pointer will eventually point to the correct insert position.

---

## ✅ Code (C++)

class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        int left = 0, right = nums.size() - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] == target) {
            return mid;
        } else if (nums[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return left; 
    }
};

⏱️ Time and Space Complexity
-> Time: O(log n) — due to binary search
-> Space: O(1) — no extra space used

🧠 Notes
-> Very efficient for large inputs due to log(n) time.
-> Left ends up as the correct insert position when the loops ends.
