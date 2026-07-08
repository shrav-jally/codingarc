MOD = 10**9 + 7
pow10 = [1] * 100001
for i in range(1, 100001):
    pow10[i] = pow10[i - 1] * 10 % MOD


class Solution:
    def sumAndMultiply(self, s: str, queries: List[List[int]]) -> List[int]:
        n = len(s)
        sum = [0] * (n + 1)
        x = [0] * (n + 1)
        cnt = [0] * (n + 1)
        for i, c in enumerate(s):
            d = int(c)
            sum[i + 1] = sum[i] + d
            x[i + 1] = (x[i] * 10 + d) % MOD if d > 0 else x[i]
            cnt[i + 1] = cnt[i] + (d > 0)

        m = len(queries)
        res = [0] * m
        for i in range(m):
            l = queries[i][0]
            r = queries[i][1] + 1
            length = cnt[r] - cnt[l]
            res[i] = (x[r] - x[l] * pow10[length]) * (sum[r] - sum[l]) % MOD

        return res
