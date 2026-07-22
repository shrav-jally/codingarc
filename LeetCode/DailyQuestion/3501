class SegmentTree:
    def __init__(self, arr):
        self.n = len(arr)
        self.arr = arr
        self.seg = [0] * (self.n << 2)

        if self.n:
            self.build(1, 0, self.n - 1)

    def build(self, p: int, l: int, r: int) -> None:
        if l == r:
            self.seg[p] = self.arr[l]
            return

        mid = (l + r) >> 1

        self.build(p << 1, l, mid)
        self.build(p << 1 | 1, mid + 1, r)

        self.seg[p] = max(self.seg[p << 1], self.seg[p << 1 | 1])

    def query(self, L: int, R: int) -> int:
        if L > R:
            return 0

        def _query(p: int, l: int, r: int) -> int:
            if L <= l and r <= R:
                return self.seg[p]

            mid = (l + r) >> 1
            res = 0

            if L <= mid:
                res = max(res, _query(p << 1, l, mid))

            if R > mid:
                res = max(res, _query(p << 1 | 1, mid + 1, r))

            return res

        return _query(1, 0, self.n - 1)


class Solution:
    def maxActiveSectionsAfterTrade(
        self, s: str, queries: List[List[int]]
    ) -> List[int]:
        n = len(s)
        cnt1 = s.count("1")

        zeroBlocks = []
        blockLeft = []
        blockRight = []

        i = 0
        while i < n:
            st = i

            while i < n and s[i] == s[st]:
                i += 1

            if s[st] == "0":
                zeroBlocks.append(i - st)
                blockLeft.append(st)
                blockRight.append(i - 1)

        m = len(zeroBlocks)
        if (
            m < 2
        ):  # continuous 0 blocks less than 2 segments, return the answer directly
            return [cnt1] * len(queries)

        tmpSum = [zeroBlocks[i] + zeroBlocks[i + 1] for i in range(m - 1)]
        seg = SegmentTree(tmpSum)
        ans = []

        for l, r in queries:
            i = bisect_left(blockRight, l)
            j = bisect_right(blockLeft, r) - 1

            # at most 1 continuous block of 0s within the substring
            if i > m - 1 or j < 0 or i >= j:
                ans.append(cnt1)
                continue

            firstLen = (
                blockRight[i] - max(blockLeft[i], l) + 1
            )  # actual length of the first consecutive block of 0s in the substring

            lastLen = (
                min(blockRight[j], r) - blockLeft[j] + 1
            )  # actual length of the last consecutive block of 0s in the substring

            # exactly 2 consecutive 0 blocks within the substring
            if i + 1 == j:
                bestGain = firstLen + lastLen
                ans.append(cnt1 + bestGain)
                continue

            val1 = firstLen + zeroBlocks[i + 1]

            val2 = zeroBlocks[j - 1] + lastLen

            val3 = seg.query(i + 1, j - 2)

            bestGain = max(val1, val2, val3)

            ans.append(cnt1 + bestGain)

        return ans
