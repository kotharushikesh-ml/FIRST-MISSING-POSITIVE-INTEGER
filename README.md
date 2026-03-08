# FIRST-MISSING-POSITIVE-INTEGER



First Missing Positive – Approach
Problem

Q) Given an unsorted integer array nums, return the smallest positive integer that is not present in the array.

Constraints:

Time Complexity: O(n)

Auxiliary Space: O(1)

Key Observation

For an array of size n, the smallest missing positive integer must lie in the range:

1 to n + 1

Example:

nums = [1,2,3]

All numbers from 1 to 3 are present, so the answer is:

4
Core Idea

Instead of using extra space like a hash table, we use the array indices to store the correct positions of numbers.

Each number x should ideally be placed at index:

x → index (x - 1)

Example mapping:

Value	Correct Index
1	0
2	1
3	2
4	3
Algorithm
Step 1: Place elements at their correct positions

Traverse the array and for each element:

If nums[i] is in the range 1..n

And it is not already at its correct position

Swap it with the element at index nums[i] - 1.

This ensures numbers are placed in their correct indices whenever possible.

Step 2: Find the first missing number

Traverse the array again:

If nums[i] != i + 1, then the missing number is:

i + 1
Step 3: If all positions are correct

If every index satisfies:

nums[i] == i + 1

then the smallest missing positive is:

n + 1
Example

Input

nums = [3,4,-1,1]

After rearranging

[1,-1,3,4]

Check indices:

Index	Expected	Actual
0	1	1
1	2	-1 ❌

So the smallest missing positive integer is:

2
Complexity Analysis

Time Complexity

O(n)

Each element is swapped at most once.

Space Complexity

O(1)

No extra data structures are used.

Pattern Used

This problem follows the Cyclic Sort / Index Placement pattern, which is commonly used in problems like:

First Missing Positive

Find Missing Number

Find All Duplicates in an Array

Set Mismatch
