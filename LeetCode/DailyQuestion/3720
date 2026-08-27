class Solution:
    def lexGreaterPermutation(self, s: str, target: str) -> str:
        cnt = [0] * 26
        for c in s:
            cnt[ord(c) - ord("a")] += 1

        n = len(target)
        res = []

        for i in range(n):
            t = ord(target[i]) - ord("a")

            # Try placing the same character as target[i]
            if cnt[t] > 0:
                cnt[t] -= 1
                # 检查能否成功
                if self.can_greater(cnt, target[i + 1 :]):
                    res.append(target[i])
                    continue
                cnt[t] += 1

            # Find a larger character
            for c in range(t + 1, 26):
                if cnt[c] > 0:
                    cnt[c] -= 1
                    res.append(chr(c + ord("a")))
                    # Lexicographically smallest permutation of remaining characters
                    res.append(
                        "".join(chr(j + ord("a")) * cnt[j] for j in range(26))
                    )
                    return "".join(res)

            # No feasible solution found
            return ""

        return ""

    def can_greater(self, cnt: list[int], suffix: str) -> bool:
        # Construct the largest string from largest to smallest
        max_str = "".join(
            chr(i + ord("a")) * cnt[i] for i in range(25, -1, -1) if cnt[i] > 0
        )
        return max_str > suffix
