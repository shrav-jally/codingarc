class Solution:
    def countMajoritySubarrays(self, nums: List[int], target: int) -> int:
        n = len(nums)
        ans = 0
        for i in range(n):
            cnt = 0
            for j in range(i, n):
                cnt += 1 if nums[j] == target else -1
                if cnt > 0:
                    ans += 1
        return ans
