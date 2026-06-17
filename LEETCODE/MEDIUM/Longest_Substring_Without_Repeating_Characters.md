# Longest Substring Without Repeating Characters

- Platform: LEETCODE
- Difficulty: MEDIUM
- URL: https://leetcode.com/problems/longest-substring-without-repeating-characters/

## Code
```java
def lengthOfLongestSubstring(s: str) -> int:
    char_set = set()
    left = 0
    max_len = 0
    for right in range(len(s)):
        while s[right] in char_set:
            char_set.remove(s[left])
            left += 1
        char_set.add(s[right])
        max_len = max(max_len, right - left + 1)
    return max_len
```

## Note
## 슬라이딩 윈도우 패턴
투 포인터(left, right)로 윈도우를 유지하며 중복 없는 최장 부분 문자열 탐색.

**시간복잡도**: O(n) — right 포인터가 한 번, left 포인터도 최대 n번 이동