class Solution:
    def processStr(self, s: str) -> str:
        result = []
        for ch in s:
            if ch == "*":
                if result:
                    result.pop()
            elif ch == "#":
                result += result.copy()
            elif ch == "%":
                result = result[::-1]
            else:
                result.append(ch)
        return "".join(result)
