## Move Zeroes

#### Python: 

```python
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        non_zero = 0
        for current in range(len(nums)):
            if nums[current] != 0:
                nums[non_zero] = nums[current]
                non_zero += 1
        for i in range(non_zero, len(nums)):
            nums[i] = 0
```