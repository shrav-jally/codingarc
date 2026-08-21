class Solution:
    def findKthSmallest(self, coins: List[int], k: int) -> int:
        coins.sort()
        n = len(coins)
        m = 1 << n
        left = k
        right = coins[0] * k + 1

        bit_count = [0] * m
        lcm = [0] * m

        for mask in range(1, m):
            cur_lcm = 1

            for i, coin in enumerate(coins):
                if mask >> i & 1:
                    cur_lcm = cur_lcm // gcd(cur_lcm, coin) * coin
                    bit_count[mask] += 1

            lcm[mask] = cur_lcm

        def count(x: int) -> int:
            res = 0

            for mask in range(1, m):
                if lcm[mask] <= x:
                    if bit_count[mask] & 1:
                        res += x // lcm[mask]
                    else:
                        res -= x // lcm[mask]

            return res

        while left < right:
            mid = (left + right) // 2

            if count(mid) >= k:
                right = mid
            else:
                left = mid + 1

        return left
