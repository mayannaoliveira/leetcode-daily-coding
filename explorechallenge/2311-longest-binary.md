## 2311. Longest Binary Subsequence Less Than or Equal to K

#### C++

```cpp
class Solution {
public:
    int longestSubsequence(string s, int k) {
        int answer = 0;
        int value = 0;
        for (int i = s.size() - 1; i >= 0; --i) {
            if (s[i] == '0') {
                ++answer;
            } else if (answer < 30 && (value | (1 << answer)) <= k) {
                value |= 1 << answer;
                ++answer;           
            }
        }
        return answer;
    }
};
```

#### Python

```python
class Solution:
    def longestSubsequence(self, s: str, k: int) -> int:
        answer = 0
        value = 0
        for i in range(len(s) - 1, -1, -1):
            if s[i] == '0':
                answer += 1
            elif answer < 30 and (value | (1 << answer)) <= k:
                value |= 1 << answer
                answer += 1
        return answer
```

