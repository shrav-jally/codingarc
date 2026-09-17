class Solution:
    def minSumOfLengths(self, arr: List[int], target: int) -> int:
        pos = {0: -1}
        n = len(arr)
        s = 0
        ans = n + 1
        min_l = n
        for i, x in enumerate(arr):
            s += x
            if s - target in pos:
                j = pos[s - target]
                length = i - j
                ans = min(ans, length + (n if j == -1 else arr[j]))
                min_l = min(min_l, length)
            arr[i] = min_l
            pos[s] = i
        return -1 if ans == n + 1 else ans
