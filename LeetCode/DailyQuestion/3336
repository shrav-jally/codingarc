class Solution:
    def subsequencePairCount(self, nums: list[int]) -> int:
        MOD = 1000000007
        m = max(nums)
        dp = [[0] * (m + 1) for _ in range(m + 1)]
        dp[0][0] = 1

        for num in nums:
            ndp = [[0] * (m + 1) for _ in range(m + 1)]

            for j in range(m + 1):
                divisor1 = math.gcd(j, num)
                for k in range(m + 1):
                    val = dp[j][k]
                    if val == 0:
                        continue

                    divisor2 = math.gcd(k, num)
                    ndp[j][k] = (ndp[j][k] + val) % MOD
                    ndp[divisor1][k] = (ndp[divisor1][k] + val) % MOD
                    ndp[j][divisor2] = (ndp[j][divisor2] + val) % MOD

            dp = ndp

        ans = 0
        for j in range(1, m + 1):
            ans = (ans + dp[j][j]) % MOD

        return ans
