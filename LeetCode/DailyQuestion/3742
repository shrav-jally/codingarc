class Solution:
    def maxPathScore(self, grid, k):
        m, n = len(grid), len(grid[0])

        INF = float("-inf")
        dp = [[[INF] * (k + 1) for _ in range(n)] for _ in range(m)]
        dp[0][0][0] = 0

        for i in range(m):
            for j in range(n):
                for c in range(k + 1):
                    if dp[i][j][c] == INF:
                        continue

                    if i + 1 < m:
                        val = grid[i + 1][j]
                        cost = 0 if val == 0 else 1
                        if c + cost <= k:
                            dp[i + 1][j][c + cost] = max(
                                dp[i + 1][j][c + cost], dp[i][j][c] + val
                            )

                    if j + 1 < n:
                        val = grid[i][j + 1]
                        cost = 0 if val == 0 else 1
                        if c + cost <= k:
                            dp[i][j + 1][c + cost] = max(
                                dp[i][j + 1][c + cost], dp[i][j][c] + val
                            )

        ans = max(dp[m - 1][n - 1])
        return -1 if ans < 0 else ans
