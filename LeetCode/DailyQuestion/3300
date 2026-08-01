class Solution:
    def minElement(self, nums: List[int]) -> int:
        ans = 37
        for num in nums:
            dig = 0
            while num > 0:
                dig += num % 10
                num //= 10
            ans = min(ans, dig)
        return ans
