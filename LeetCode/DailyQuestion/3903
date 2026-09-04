class Solution:
    def firstStableIndex(self, nums: list[int], k: int) -> int:
        n = len(nums)
        for i in range(n):
            maxValue = minValue = nums[i]
            for j in range(i):
                maxValue = max(maxValue, nums[j])
            for j in range(i + 1, n):
                minValue = min(minValue, nums[j])
            if maxValue - minValue <= k:
                return i
        return -1
