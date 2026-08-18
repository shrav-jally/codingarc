class Solution:
    def minimumDistance(self, nums: List[int]) -> int:
        n = len(nums)
        nxt = [-1] * n
        occur = {}
        ans = n + 1

        for i in range(n - 1, -1, -1):
            if nums[i] in occur:
                nxt[i] = occur[nums[i]]
            occur[nums[i]] = i

        for i in range(n):
            second_pos = nxt[i]
            if second_pos != -1:
                third_pos = nxt[second_pos]
                if third_pos != -1:
                    ans = min(ans, third_pos - i)

        return -1 if ans == n + 1 else ans * 2
