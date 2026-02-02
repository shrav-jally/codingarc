class Container:
    def __init__(self, k: int):
        self.k = k
        self.st1 = SortedList()
        self.st2 = SortedList()
        self.sm = 0

    def adjust(self):
        while len(self.st1) < self.k and len(self.st2) > 0:
            x = self.st2[0]
            self.st1.add(x)
            self.st2.remove(x)
            self.sm += x

        while len(self.st1) > self.k:
            x = self.st1[-1]
            self.st2.add(x)
            self.st1.remove(x)
            self.sm -= x

    # insert element x
    def add(self, x: int):
        if len(self.st2) > 0 and x >= self.st2[0]:
            self.st2.add(x)
        else:
            self.st1.add(x)
            self.sm += x
        self.adjust()

    # delete element x
    def erase(self, x: int):
        if x in self.st1:
            self.st1.remove(x)
            self.sm -= x
        elif x in self.st2:
            self.st2.remove(x)
        self.adjust()

    # sum of the first k smallest elements
    def sum(self) -> int:
        return self.sm


class Solution:
    def minimumCost(self, nums: List[int], k: int, dist: int) -> int:
        n = len(nums)
        cnt = Container(k - 2)
        for i in range(1, k - 1):
            cnt.add(nums[i])

        ans = cnt.sum() + nums[k - 1]
        for i in range(k, n):
            j = i - dist - 1
            if j > 0:
                cnt.erase(nums[j])
            cnt.add(nums[i - 1])
            ans = min(ans, cnt.sum() + nums[i])

        return ans + nums[0]
