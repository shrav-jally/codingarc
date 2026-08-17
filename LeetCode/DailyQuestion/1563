class Solution:
    def stoneGameV(self, stoneValue: List[int]) -> int:
        @lru_cache(None)
        def dfs(left: int, right: int) -> int:
            if left == right:
                return 0

            total = sum(stoneValue[left : right + 1])
            suml = ans = 0
            for i in range(left, right):
                suml += stoneValue[i]
                sumr = total - suml
                if suml < sumr:
                    ans = max(ans, dfs(left, i) + suml)
                elif suml > sumr:
                    ans = max(ans, dfs(i + 1, right) + sumr)
                else:
                    ans = max(ans, max(dfs(left, i), dfs(i + 1, right)) + suml)
            return ans

        n = len(stoneValue)
        return dfs(0, n - 1)
