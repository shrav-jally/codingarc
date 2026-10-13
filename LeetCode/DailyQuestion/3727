class Solution:
    def maxAlternatingSum(self, nums: List[int]) -> int:
        n = len(nums)
        for i in range(n):
            nums[i] *= nums[i]
        nums.sort()
        return -sum(nums[: n // 2]) + sum(nums[n // 2 :])
