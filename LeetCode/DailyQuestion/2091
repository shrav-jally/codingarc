class Solution:
    def minimumDeletions(self, nums: List[int]) -> int:
        minidx = nums.index(min(nums))
        maxidx = nums.index(max(nums))
        l = min(minidx, maxidx)  # The smaller value in the most valuable index
        r = max(minidx, maxidx)  # The bigger value in the most valuable index
        n = len(nums)
        return min(
            r + 1, n - l, l + 1 + n - r
        )  # Calculate the minimum number of deletions in three cases
