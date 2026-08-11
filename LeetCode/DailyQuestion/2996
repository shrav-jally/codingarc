class Solution:
    def missingInteger(self, nums: list[int]) -> int:
        total = nums[0]

        for a, b in pairwise(nums):
            if b == a + 1:
                total += b
            else:
                break

        num_set = set(nums)

        while total in num_set:
            total += 1

        return total
