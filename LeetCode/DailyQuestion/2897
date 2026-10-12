class Solution:
    def maxSum(self, nums: List[int], k: int) -> int:
        MOD = 10**9 + 7
        cnt = [0] * 30

        # Count the number of 1 bits at each position
        for num in nums:
            for i in range(30):
                if num & (1 << i):
                    cnt[i] += 1

        res = 0
        for _ in range(k):
            cur = 0
            # Construct the current number from the most significant bit to the least significant bit
            for j in range(29, -1, -1):
                if cnt[j] > 0:
                    cur |= 1 << j
                    cnt[j] -= 1
            res = (res + cur * cur) % MOD

        return res
