class Solution:
    def minInsertions(self, s: str) -> int:
        length = len(s)
        insertions = left_count = index = 0

        while index < length:
            if s[index] == "(":
                left_count += 1
                index += 1
            else:
                if left_count > 0:
                    left_count -= 1
                else:
                    insertions += 1
                if index < length - 1 and s[index + 1] == ")":
                    index += 2
                else:
                    insertions += 1
                    index += 1

        insertions += left_count * 2
        return insertions
