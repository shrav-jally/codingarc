class Solution:
    def firstStableIndex(self, nums: list[int], k: int) -> int:
        n = len(nums)
        minValue = [inf] * (n - 1) + [nums[-1]]
        for i in range(n - 2, -1, -1):
            minValue[i] = min(minValue[i + 1], nums[i])

        maxValue = 0
        for i in range(n):
            maxValue = max(maxValue, nums[i])
            if maxValue - minValue[i] <= k:
                return i
        return -1
