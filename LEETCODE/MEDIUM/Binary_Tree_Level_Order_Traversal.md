# Binary Tree Level Order Traversal

- Platform: LEETCODE
- Difficulty: MEDIUM
- URL: https://leetcode.com/problems/binary-tree-level-order-traversal/

## Code
```java
from collections import deque
def levelOrder(root):
    if not root: return []
    result, queue = [], deque([root])
    while queue:
        level = []
        for _ in range(len(queue)):
            node = queue.popleft()
            level.append(node.val)
            if node.left: queue.append(node.left)
            if node.right: queue.append(node.right)
        result.append(level)
    return result
```

## Note
## BFS 레벨 순회
---
deque를 사용하여 각 레벨의 노드를 그룹핑.

핵심: 매 반복마다 현재 큐 길이만큼만 처리하여 레벨 구분.