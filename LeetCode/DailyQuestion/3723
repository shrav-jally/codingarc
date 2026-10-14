class Solution:
    def maxSumOfSquares(self, num: int, sum: int) -> str:
        if sum > 9 * num:
            return ""
        q, r = divmod(sum, 9)
        ans = "9" * q
        if r > 0:
            ans += str(r)
        ans += "0" * (num - len(ans))
        return ans
