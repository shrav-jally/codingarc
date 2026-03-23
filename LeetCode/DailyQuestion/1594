class Solution:
    def maxProductPath(self, grid: List[List[int]]) -> int:
        mod = 10**9 + 7
        m, n = len(grid), len(grid[0])
        maxgt = [[0] * n for _ in range(m)]
        minlt = [[0] * n for _ in range(m)]

        maxgt[0][0] = minlt[0][0] = grid[0][0]
        for i in range(1, n):
            maxgt[0][i] = minlt[0][i] = maxgt[0][i - 1] * grid[0][i]
        for i in range(1, m):
            maxgt[i][0] = minlt[i][0] = maxgt[i - 1][0] * grid[i][0]

        for i in range(1, m):
            for j in range(1, n):
                if grid[i][j] >= 0:
                    maxgt[i][j] = (
                        max(maxgt[i][j - 1], maxgt[i - 1][j]) * grid[i][j]
                    )
                    minlt[i][j] = (
                        min(minlt[i][j - 1], minlt[i - 1][j]) * grid[i][j]
                    )
                else:
                    maxgt[i][j] = (
                        min(minlt[i][j - 1], minlt[i - 1][j]) * grid[i][j]
                    )
                    minlt[i][j] = (
                        max(maxgt[i][j - 1], maxgt[i - 1][j]) * grid[i][j]
                    )

        if maxgt[m - 1][n - 1] < 0:
            return -1
        return maxgt[m - 1][n - 1] % mod
