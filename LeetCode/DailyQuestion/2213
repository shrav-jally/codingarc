class Solution:
    def longestRepeating(
        self, s: str, queryCharacters: str, queryIndices: List[int]
    ) -> List[int]:
        n = len(s)
        pre = [0] * (4 * n)
        suf = [0] * (4 * n)
        maxLen = [0] * (4 * n)
        leftChar = [""] * (4 * n)
        rightChar = [""] * (4 * n)

        def build(u: int, l: int, r: int) -> None:
            if l == r:
                pre[u] = 1
                suf[u] = 1
                maxLen[u] = 1
                leftChar[u] = s[l]
                rightChar[u] = s[l]
                return
            mid = (l + r) >> 1
            build(u << 1, l, mid)
            build(u << 1 | 1, mid + 1, r)
            pushUp(u, l, r)

        def pushUp(u: int, l: int, r: int) -> None:
            mid = (l + r) >> 1
            leftLen = mid - l + 1
            rightLen = r - mid
            left = u << 1
            right = u << 1 | 1
            leftChar[u] = leftChar[left]
            rightChar[u] = rightChar[right]
            pre[u] = pre[left]
            if pre[left] == leftLen and rightChar[left] == leftChar[right]:
                pre[u] = pre[left] + pre[right]
            suf[u] = suf[right]
            if suf[right] == rightLen and rightChar[left] == leftChar[right]:
                suf[u] = suf[right] + suf[left]
            maxLen[u] = max(maxLen[left], maxLen[right])
            if rightChar[left] == leftChar[right]:
                maxLen[u] = max(maxLen[u], suf[left] + pre[right])

        def update(u: int, l: int, r: int, pos: int, ch: str) -> None:
            if l == r:
                leftChar[u] = ch
                rightChar[u] = ch
                return
            mid = (l + r) >> 1
            if pos <= mid:
                update(u << 1, l, mid, pos, ch)
            else:
                update(u << 1 | 1, mid + 1, r, pos, ch)
            pushUp(u, l, r)

        build(1, 0, n - 1)
        k = len(queryIndices)
        ans = []
        for i in range(k):
            update(1, 0, n - 1, queryIndices[i], queryCharacters[i])
            ans.append(maxLen[1])
        return ans
