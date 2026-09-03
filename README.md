# Leetcode_Day33
# Day 33 – Merge Sorted Array

## LeetCode 88: Merge Sorted Array

**Difficulty:** Easy

### Problem

You are given two integer arrays `nums1` and `nums2`, both sorted in non-decreasing order.

- `nums1` contains `m` valid elements followed by `n` empty spaces (`0`s).
- `nums2` contains `n` elements.
- The goal is to merge both arrays into `nums1` in sorted order.

### Example

**Input:**
```text
nums1 = [1,2,3,0,0,0], m = 3
nums2 = [2,5,6], n = 3

Output:

[1,2,2,3,5,6]
Approach

For today's solution, I used an ArrayList:

Add the first m valid elements of nums1 to the list.
Add all elements of nums2 to the list.
Sort the complete list using Collections.sort().
Copy the sorted elements back into nums1.
Code
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        ArrayList<Integer> list = new ArrayList<>();

        for (int i = 0; i < m; i++) {
            list.add(nums1[i]);
        }

        for (int i = 0; i < n; i++) {
            list.add(nums2[i]);
        }

        Collections.sort(list);

        for (int i = 0; i < m + n; i++) {
            nums1[i] = list.get(i);
        }
    }
}
Complexity
Time Complexity: O((m + n) log(m + n))
Space Complexity: O(m + n)
What I Learned

This problem reminded me that there can be multiple ways to solve the same problem.

My approach works by combining everything first and then sorting it. However, since both arrays are already sorted, there is a more optimized approach using the two-pointer technique that can merge them in O(m + n) time.

The important lesson for me today was not just getting an accepted solution, but understanding how the given constraints and properties of the input can help us improve an approach.

Key Takeaway

An accepted solution is the starting point for learning, not always the final point of optimization.
