class Solution:
    def gcdValues(self, nums: List[int], queries: List[int]) -> List[int]:
        m = max(nums)
        cnt = [0] * (m + 1)
        for num in nums:
            cnt[num] += 1
        for i in range(1, m + 1):
            for j in range(i * 2, m + 1, i):
                cnt[i] += cnt[j]
        for i in range(1, m + 1):
            cnt[i] = cnt[i] * (cnt[i] - 1) // 2
        for i in range(m, 0, -1):
            for j in range(i * 2, m + 1, i):
                cnt[i] -= cnt[j]
        for i in range(1, m + 1):
            cnt[i] += cnt[i - 1]
        ans = []
        for q in queries:
            q += 1
            pos = bisect_left(cnt, q)
            ans.append(pos)
        return ans
