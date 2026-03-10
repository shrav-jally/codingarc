class Solution:
    def numberOfStableArrays(self, zero: int, one: int, limit: int) -> int:
        mod = 10**9 + 7

        @cache
        def dp(zero, one, lastBit):
            if zero == 0:
                if lastBit == 0 or one > limit:
                    return 0
                else:
                    return 1
            elif one == 0:
                if lastBit == 1 or zero > limit:
                    return 0
                else:
                    return 1
            if lastBit == 0:
                res = dp(zero - 1, one, 0) + dp(zero - 1, one, 1)
                if zero > limit:
                    res -= dp(zero - limit - 1, one, 1)
            else:
                res = dp(zero, one - 1, 0) + dp(zero, one - 1, 1)
                if one > limit:
                    res -= dp(zero, one - limit - 1, 0)
            return res % mod

        res = (dp(zero, one, 0) + dp(zero, one, 1)) % mod
        dp.cache_clear()
        return res
