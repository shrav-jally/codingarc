class Solution:
    def removeOuterParentheses(self, s: str) -> str:
        res, stack = [], []
        for c in s:
            if c == ")":
                stack.pop()
            if stack:
                res.append(c)
            if c == "(":
                stack.append(c)
        return "".join(res)
