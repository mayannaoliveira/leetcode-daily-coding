## Duplicate Zeros

#### Python: 

```python
class Solution:
    def duplicateZeros(self, arr: List[int]) -> None:
        """
        Do not return anything, modify arr in-place instead.
        """
        n = len(arr)
        zero_count = arr.count(0)
        i = n - 1
        j = n + zero_count - 1
        while i >= 0 and j >= 0:
            if arr[i] != 0:
                if j < n:
                    arr[j] = arr[i]
            else:
                if j < n:
                    arr[j] = 0
                j -= 1
                if j < n:
                    arr[j] = 0
            i -= 1
            j -= 1
```