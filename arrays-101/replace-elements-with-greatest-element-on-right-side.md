## Replace Elements with Greatest Element on Right Side

#### Python: 

```python
class Solution:
    def replaceElements(self, arr: List[int]) -> List[int]:
        if not arr:
            return []
        n = len(arr)
        max_so_far = -1
        for i in range(n-1, -1, -1):
            current = arr[i]
            arr[i] = max_so_far
            if current > max_so_far:
                max_so_far = current
        return arr
```

:card_file_box: Return to [Table of Contents](README.md).