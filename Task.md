## Question 1
## Two Sum
<img width="647" alt="image" src="https://github.com/vaish0825/leetcode-python-easy/assets/171915053/928509a3-0988-43a3-b9ed-6029897899c2">

## Answer

class Solution(object):
    def twoSum(self, nums, target):
        hash_map = {}
        
        for i,num in enumerate(nums):
            if target - num in hash_map:
               return [hash_map[target-num],i] #hash_map[2]
            hash_map[num] = i

        return []




