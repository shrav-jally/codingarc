class Solution:
    def maxBuilding(self, n: int, restrictions: List[List[int]]) -> int:
        r = restrictions
        # Add restriction (1, 0)
        r.append([1, 0])
        r.sort()

        # Add restriction (n, n-1)
        if r[-1][0] != n:
            r.append([n, n - 1])

        m = len(r)

        # Pass restrictions from left to right
        for i in range(1, m):
            r[i][1] = min(r[i][1], r[i - 1][1] + (r[i][0] - r[i - 1][0]))
        # Pass restrictions from right to left
        for i in range(m - 2, 0, -1):
            r[i][1] = min(r[i][1], r[i + 1][1] + (r[i + 1][0] - r[i][0]))

        ans = 0
        for i in range(m - 1):
            # Calculate the maximum height of the buildings between r[i][0] and r[i][1]
            best = ((r[i + 1][0] - r[i][0]) + r[i][1] + r[i + 1][1]) // 2
            ans = max(ans, best)

        return ans
