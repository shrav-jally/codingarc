class Solution:
    MOD = 10**9 + 7

    def xorAfterQueries(self, nums: List[int], queries: List[List[int]]) -> int:
        for l, r, k, v in queries:
            for i in range(l, r + 1, k):
                nums[i] = (nums[i] * v) % self.MOD

        res = 0
        for x in nums:
            res ^= x

        return res
