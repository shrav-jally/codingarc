class Solution:
    def maximumAmount(self, coins: List[List[int]]) -> int:
        m, n = len(coins), len(coins[0])

        dp = [[[-inf] * 3 for _ in range(n)] for _ in range(m)]

        dp[0][0][0] = coins[0][0]
        for k in range(1, 3):
            dp[0][0][k] = max(coins[0][0], 0)

        for j in range(1, n):
            for k in range(3):
                dp[0][j][k] = dp[0][j - 1][k] + coins[0][j]
                if k > 0:
                    dp[0][j][k] = max(
                        dp[0][j][k], dp[0][j - 1][k - 1] + max(coins[0][j], 0)
                    )

        for i in range(1, m):
            for k in range(3):
                dp[i][0][k] = dp[i - 1][0][k] + coins[i][0]
                if k > 0:
                    dp[i][0][k] = max(
                        dp[i][0][k], dp[i - 1][0][k - 1] + max(coins[i][0], 0)
                    )

        for i in range(1, m):
            for j in range(1, n):
                for k in range(3):
                    dp[i][j][k] = (
                        max(dp[i - 1][j][k], dp[i][j - 1][k]) + coins[i][j]
                    )

                    if k > 0:
                        dp[i][j][k] = max(
                            dp[i][j][k],
                            max(dp[i - 1][j][k - 1], dp[i][j - 1][k - 1]),
                        )

        return dp[m - 1][n - 1][2]
