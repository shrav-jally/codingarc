class Solution:
    def specialTriplets(self, nums: List[int]) -> int:
        MOD = 10**9 + 7
        num_cnt = {}
        num_partial_cnt = {}

        for v in nums:
            num_cnt[v] = num_cnt.get(v, 0) + 1

        ans = 0
        for v in nums:
            target = v * 2
            l_cnt = num_partial_cnt.get(target, 0)
            num_partial_cnt[v] = num_partial_cnt.get(v, 0) + 1
            r_cnt = num_cnt.get(target, 0) - num_partial_cnt.get(target, 0)
            ans = (ans + l_cnt * r_cnt) % MOD

        return ans
