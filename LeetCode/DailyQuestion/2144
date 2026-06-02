class Solution:
    def minimumCost(self, cost: List[int]) -> int:
        cost.sort(key=lambda x: -x)
        res = 0
        n = len(cost)
        for i in range(n):
            if i % 3 != 2:
                res += cost[i]
        return res
