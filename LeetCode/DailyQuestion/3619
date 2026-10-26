class Solution:
    def countIslands(self, grid: List[List[int]], k: int) -> int:
        m, n = len(grid), len(grid[0])
        dirs = (-1, 0, 1, 0, -1)

        def dfs(i: int, j: int) -> int:
            total = grid[i][j]
            grid[i][j] = 0
            for d in range(4):
                x, y = i + dirs[d], j + dirs[d + 1]
                if 0 <= x < m and 0 <= y < n and grid[x][y] > 0:
                    total += dfs(x, y)
            return total

        return sum(
            grid[i][j] > 0 and dfs(i, j) % k == 0
            for i in range(m)
            for j in range(n)
        )
