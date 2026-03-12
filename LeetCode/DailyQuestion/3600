class DSU:
    def __init__(self, parent):
        self.parent = parent

    def find(self, x):
        if self.parent[x] == x:
            return x
        self.parent[x] = self.find(self.parent[x])
        return self.parent[x]

    def join(self, x, y):
        px = self.find(x)
        py = self.find(y)
        self.parent[px] = py


MAX_STABILITY = 200000


class Solution:
    def maxStability(self, n: int, edges: List[List[int]], k: int) -> int:
        ans = -1

        if len(edges) < n - 1:
            return -1

        mustEdges = [e for e in edges if e[3] == 1]
        optionalEdges = [e for e in edges if e[3] != 1]

        if len(mustEdges) > n - 1:
            return -1

        optionalEdges.sort(key=lambda x: x[2], reverse=True)

        selectedInit = 0
        mustMinStability = MAX_STABILITY
        dsuInit = DSU(list(range(n)))

        for u, v, s, must in mustEdges:
            if dsuInit.find(u) == dsuInit.find(v) or selectedInit == n - 1:
                return -1
            dsuInit.join(u, v)
            selectedInit += 1
            mustMinStability = min(mustMinStability, s)

        l = 0
        r = mustMinStability

        while l < r:
            mid = l + ((r - l + 1) >> 1)
            dsu = DSU(dsuInit.parent[:])
            selected = selectedInit
            doubledCount = 0

            for u, v, s, must in optionalEdges:
                if dsu.find(u) == dsu.find(v):
                    continue

                if s >= mid:
                    dsu.join(u, v)
                    selected += 1
                elif doubledCount < k and s * 2 >= mid:
                    doubledCount += 1
                    dsu.join(u, v)
                    selected += 1
                else:
                    break

                if selected == n - 1:
                    break

            if selected != n - 1:
                r = mid - 1
            else:
                ans = l = mid

        return ans
