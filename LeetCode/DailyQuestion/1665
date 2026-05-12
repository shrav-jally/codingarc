class Solution:
    def minimumEffort(self, tasks: List[List[int]]) -> int:
        tasks.sort(key=lambda x: x[1] - x[0], reverse=True)
        ans = 0
        remain = 0
        for task in tasks:
            if remain <= task[1]:
                ans += task[1] - remain
            remain = max(task[1] - task[0], remain - task[0])
        return ans
