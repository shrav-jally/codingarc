class Solution:
    def minOperations(self, s: str, k: int) -> int:
        n, m = len(s), s.count("0")
        dist = [math.inf] * (n + 1)
        nodeSets = [
            SortedList(range(0, n + 1, 2)),
            SortedList(range(1, n + 1, 2)),
        ]
        q = deque([m])
        dist[m] = 0
        nodeSets[m % 2].remove(m)
        while q:
            m = q.popleft()
            c1, c2 = max(k - n + m, 0), min(m, k)
            lnode, rnode = m + k - 2 * c2, m + k - 2 * c1
            nodeSet = nodeSets[lnode % 2]
            idx = nodeSet.bisect_left(lnode)
            while idx < len(nodeSet) and nodeSet[idx] <= rnode:
                m2 = nodeSet[idx]
                dist[m2] = dist[m] + 1
                q.append(m2)
                nodeSet.pop(idx)
        return -1 if dist[0] == math.inf else dist[0]
