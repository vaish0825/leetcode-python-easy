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

## Answer
   
    class Solution(object):
        def isPalindrome(self, x):
        
        s = str(x)
        
        # Initialize pointers
        left, right = 0, len(s) - 1
        
        # Compare characters from left and right towards the center
        while left <= right:
            if s[left] != s[right]:
                return False
            left += 1
            right -= 1
        
        return True
## Explanation
   Certainly! Let's walk through the provided Python code step by step, and I'll explain how it checks whether an integer `x` is a palindrome.

```python
class Solution(object):
    def isPalindrome(self, x):
        # Convert integer to string
        s = str(x)
        
        # Initialize pointers
        left, right = 0, len(s) - 1
        
        # Compare characters from left and right towards the center
        while left <= right:
            if s[left] != s[right]:
                return False
            left += 1
            right -= 1
        
        return True
```

### Explanation:

1. **Class Definition**:
   - `class Solution(object):` defines a class named `Solution`. In Python, classes are used to encapsulate related functions and data.

2. **Method Definition**:
   - `def isPalindrome(self, x):` defines a method `isPalindrome` within the `Solution` class. This method takes `self` (which refers to the instance of the class itself) and `x` (the integer to check for palindrome) as parameters.

3. **Convert Integer to String**:
   - `s = str(x)`: Converts the integer `x` to a string `s`. This allows us to treat `x` as a sequence of characters for easier comparison.

4. **Initialize Pointers**:
   - `left, right = 0, len(s) - 1`: Initializes two pointers, `left` starting at the beginning (`0`) of the string `s`, and `right` starting at the end (`len(s) - 1`). This prepares us to compare characters from opposite ends towards the center.

5. **Check Palindrome Condition**:
   - `while left <= right:`: This loop continues until the `left` pointer is greater than the `right` pointer, which means we have checked all relevant pairs of characters.
     - `if s[left] != s[right]:` checks if the characters at positions `left` and `right` in the string `s` are not equal.
       - If they are not equal, it means `x` is not a palindrome, so `False` is returned.
     - `left += 1` and `right -= 1`: Moves the `left` pointer one step right and the `right` pointer one step left, narrowing down the comparison range.

6. **Return True for Palindrome**:
   - If the loop completes without finding unequal characters (`left > right`), all characters have matched, and `x` is a palindrome. Hence, `True` is returned.

### Example Walkthrough:

Let's walk through an example to illustrate how the code works:

- **Input**: `x = 121`
  - Convert integer to string: `s = "121"`
  - `left = 0`, `right = 2`
  - Compare `s[0]` and `s[2]`: `1 == 1`
  - Move pointers: `left = 1`, `right = 1`
  - Compare `s[1]` and `s[1]`: `2 == 2`
  - `left` is now greater than `right`, return `True`.

- **Input**: `x = -121`
  - Since `x` is negative, return `False` immediately.

- **Input**: `x = 10`
  - Convert integer to string: `s = "10"`
  - `left = 0`, `right = 1`
  - Compare `s[0]` and `s[1]`: `1 != 0`
  - Return `False`.

### Complexity:
- **Time Complexity**: O(n), where n is the number of digits in the integer `x`. Converting `x` to a string takes O(n) time, and checking if it's a palindrome also takes O(n) time.
- **Space Complexity**: O(n) for storing the string `s`.

This approach efficiently determines if `x` is a palindrome using string manipulation and is optimal for the given constraints.
## Question 3
## Roman Integer
<img width="443" alt="image" src="https://github.com/vaish0825/leetcode-python-easy/assets/171915053/2795966b-c023-42f7-9166-542049b22200">
<img width="436" alt="image" src="https://github.com/vaish0825/leetcode-python-easy/assets/171915053/4bceea17-f49d-4c0a-acde-edc9a4588dd8">
<img width="382" alt="image" src="https://github.com/vaish0825/leetcode-python-easy/assets/171915053/ba18d2ed-a559-407a-acdd-3596d6eac6db">

## Explanation
   The provided `Solution` class is a Python implementation of a function `romanToInt` that converts a Roman numeral string `s` into its corresponding integer value. Let's break down the code and ensure clarity on how it works:

### Explanation of the Code:

1. **Symbol Hash**:
   - `symbol_hash` is a dictionary that maps Roman numeral symbols and their combinations to their respective integer values. This includes mappings like `'I'` to `1`, `'IV'` to `4`, `'V'` to `5`, etc. This allows us to efficiently look up the value of Roman numeral combinations during the conversion process.

2. **Initialization**:
   - `integer` is initialized to `0`. This variable will accumulate the total integer value of the Roman numeral string.
   - `i` is initialized to `0`, which will be used as an index to traverse through the string `s`.

3. **Conversion Loop**:
   - The `while` loop continues as long as `i` is less than the length of `s`.
   - Inside the loop:
     - `two_val = symbol_hash.get(s[i:i + 2])`: Attempts to retrieve the value from `symbol_hash` corresponding to the substring of length 2 starting from index `i`. This checks for cases like `'IV'`, `'IX'`, etc.
     - If `two_val` is not `None` (meaning the substring exists in `symbol_hash`):
       - Add `two_val` to `integer`.
       - Increment `i` by 2 to move past the two-character Roman numeral substring.
     - If `two_val` is `None` (the substring doesn't exist in `symbol_hash`):
       - Add the value of `s[i]` (which represents a single Roman numeral character) to `integer`.
       - Increment `i` by 1 to move to the next character in `s`.

4. **Return**:
   - Once the loop completes (when `i` is equal to or exceeds the length of `s`), `integer` contains the total integer value corresponding to the Roman numeral string `s`. Return this value as the result of the function.

### Example Usage:

Here's how you would use the `Solution` class:

```python
class Solution(object):
    def romanToInt(self, s):
        symbol_hash = {
            'I': 1,
            'IV': 4,
            'V': 5,
            'IX': 9,
            'X': 10,
            'XL': 40,
            'L': 50,
            'XC': 90,
            'C': 100,
            'CD': 400,
            'D': 500,
            'CM': 900,
            'M': 1000,
        }

        integer = 0
        i = 0
        while i < len(s):
            two_val = symbol_hash.get(s[i:i + 2])
            if two_val:
                integer += two_val
                i += 2
            else:
                integer += symbol_hash[s[i]]
                i += 1
        return integer

# Example usage:
solution = Solution()
print(solution.romanToInt("III"))       # Output: 3
print(solution.romanToInt("LVIII"))     # Output: 58
print(solution.romanToInt("MCMXCIV"))   # Output: 1994
```

### Summary:

This implementation efficiently converts valid Roman numeral strings into their corresponding integer values using a dictionary for quick lookups of numeral combinations. It follows the rules of Roman numeral representation where smaller numerals preceding larger ones denote subtraction. The function handles the input string `s` correctly and returns the expected integer values for various Roman numeral examples provided.
   
   
   
   
   
   


   
