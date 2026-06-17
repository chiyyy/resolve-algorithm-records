# Two Sum

- Platform: LEETCODE
- Difficulty: MEDIUM
- URL: https://leetcode.com/problems/two-sum/

## Code
```java
def twoSum(nums, target):
    seen = {}
    for i, n in enumerate(nums):
        diff = target - n
        if diff in seen:
            return [seen[diff], i]
        seen[n] = i
```

## Note
## 풀이 접근법
해시맵을 사용하여 O(n) 시간복잡도로 해결.

- 각 원소를 순회하며 **보완 값(target - n)** 을 해시맵에서 탐색
- 존재하면 즉시 반환, 없으면 현재 값을 저장

### 핵심 인사이트
투 포인터로도 풀 수 있지만, 정렬이 필요하여 인덱스가 바뀜 → 해시맵이 더 적합