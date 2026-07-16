class Solution:
    def gcdSum(self, nums: list[int]) -> int:
        n = len(nums)
        mx = []
        prefixMax = -inf

        for x in nums:
            prefixMax = max(prefixMax, x)
            mx.append(prefixMax)

        prefixGcd = [gcd(x, y) for x, y in zip(nums, mx)]
        prefixGcd.sort()

        ans = 0
        left, right = 0, n - 1
        while left < right:
            ans += gcd(prefixGcd[left], prefixGcd[right])
            left += 1
            right -= 1
        return ans
