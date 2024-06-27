## Question 1
## Two Sum
<img width="647" alt="image" src="https://github.com/vaish0825/leetcode-python-easy/assets/171915053/928509a3-0988-43a3-b9ed-6029897899c2">

### Answer
    class Solution(object):
    def twoSum(self, nums, target):
        hash_map = {}
        
        for i, num in enumerate(nums):
            if target - num in hash_map:
               return [hash_map[target-num], i]
            hash_map[num] = i

        return []

### Explanation
The `twoSum` function in the provided code is a Python method designed to find two numbers in an array `nums` that add up to a specified `target`. Let's break down how it works:

```python
class Solution(object):
    def twoSum(self, nums, target):
        hash_map = {}
        
        for i, num in enumerate(nums):
            if target - num in hash_map:
               return [hash_map[target-num], i]
            hash_map[num] = i

        return []
```

### Explanation:

1. **Initialization**:
   - `hash_map = {}`: This dictionary (`hash_map`) will store elements of `nums` as keys and their indices as values.

2. **Loop through `nums`**:
   - `for i, num in enumerate(nums)`: This iterates through each element (`num`) in `nums` along with its index (`i`).

3. **Check complement in `hash_map`**:
   - `if target - num in hash_map:`: Checks if the complement of `num` (i.e., `target - num`) exists as a key in `hash_map`.
     - If it exists, it means that `target - num` was previously encountered in `nums` and its index is stored in `hash_map[target - num]`. Therefore, we found two indices (`hash_map[target-num]` and `i`) whose corresponding elements sum up to `target`.
     - Returns `[hash_map[target-num], i]`, which are the indices of the two numbers in `nums`.

4. **Store current number and index**:
   - `hash_map[num] = i`: If the complement is not found, store the current number `num` as a key in `hash_map` with its index `i`.

5. **Return an empty list if no solution**:
   - If the loop completes without finding a valid pair, return an empty list `[]`.

### Example:
For `nums = [2, 7, 11, 15]` and `target = 9`:
- Iteration 1: `num = 2`, `target - num = 7`. `hash_map` is `{2: 0}`.
- Iteration 2: `num = 7`, `target - num = 2`. `hash_map` contains `2`, so return `[0, 1]`.

This algorithm has a time complexity of O(n), where n is the number of elements in `nums`, because each lookup and insertion operation in a dictionary (hash map) is average O(1). Therefore, the overall complexity is dominated by the single loop through `nums`.

## Question 2
## Palindrome Number
<img width="451" alt="image" src="https://github.com/vaish0825/leetcode-python-easy/assets/171915053/c0fe7313-d076-4d17-976e-754d0df812c8">

    











