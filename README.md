# 🧮 Two Sum

## 🔗 Problem Link
https://leetcode.com/problems/two-sum/

---

## 📌 Problem Statement
Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to the target.

You may assume that each input has exactly one solution, and you may not use the same element twice.

---

## 💡 Approach (Optimized - HashMap)

- Use a Dictionary to store numbers and their indices
- For each element:
  - Calculate complement = target - current number
  - Check if complement exists in dictionary
  - If yes → return indices
  - Otherwise → store current number in dictionary

---

## 🧾 Code (C#)

```csharp
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        Dictionary<int, int> map = new Dictionary<int, int>();

        for (int i = 0; i < nums.Length; i++) {
            int complement = target - nums[i];

            if (map.ContainsKey(complement)) {
                return new int[] { map[complement], i };
            }

            map[nums[i]] = i;
        }

        return new int[] {};
    }
}
