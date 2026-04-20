class Solution:
    def maxDistance(self, colors: List[int]) -> int:
        n = len(colors)
        res = 0  # the maximum distance between two houses of different colors
        # traverse the indices of two houses and maintain the maximum distance
        for i in range(n):
            for j in range(i + 1, n):
                if colors[i] != colors[j]:
                    res = max(res, j - i)
        return res
