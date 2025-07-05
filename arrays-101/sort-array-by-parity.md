## Sort Array By Parity

#### Python: 

```python
class Solution:
    def sortArrayByParity(self, nums: List[int]) -> List[int]:
        left, right = 0, len(nums) - 1
        while left < right:
            if nums[left] % 2 == 1 and nums[right] % 2 == 0:
                # Swap if left is odd and right is even
                nums[left], nums[right] = nums[right], nums[left]
                left += 1
                right -= 1
            else:
                if nums[left] % 2 == 0:
                    left += 1
                if nums[right] % 2 == 1:
                    right -= 1
        return nums
```
