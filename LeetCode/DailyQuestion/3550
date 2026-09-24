class Solution:
    def smallestIndex(self, nums: list[int]) -> int:
        def get_digit_sum(num: int) -> int:
            total = 0

            while num:
                num, digit = divmod(num, 10)
                total += digit

            return total

        for i, num in enumerate(nums):
            if get_digit_sum(num) == i:
                return i

        return -1
