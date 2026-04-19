class Solution:
    def closestTarget(
        self, words: List[str], target: str, startIndex: int
    ) -> int:
        ans = n = len(words)
        for i, word in enumerate(words):
            if word == target:
                ans = min(ans, abs(i - startIndex), n - abs(i - startIndex))
        return ans if ans < n else -1
