class Solution:
    def numberOfSets(self, n: int, k: int) -> int:
        mod = 10**9 + 7
        dp = [1] * n
        prefix_sums = [0] * (n + 1)
        for j in range(n):
            prefix_sums[j + 1] = (prefix_sums[j] + dp[j]) % mod
        for _ in range(k):
            dp[0] = 0
            for j in range(1, n):
                dp[j] = (dp[j - 1] + prefix_sums[j]) % mod
            for j in range(n):
                prefix_sums[j + 1] = (prefix_sums[j] + dp[j]) % mod
        return dp[n - 1]
