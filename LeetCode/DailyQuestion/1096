class Solution:
    def braceExpansionII(self, expression: str) -> List[str]:
        idx = 0
        n = len(expression)

        def is_letter(c: str) -> bool:
            return "a" <= c <= "z"

        # Recursive descent parser
        def expr() -> set:
            nonlocal idx
            ret = set()
            while True:
                # Take the union with the result of term()
                ret |= term()
                # Continue if a comma is matched; otherwise, stop matching
                if idx < n and expression[idx] == ",":
                    idx += 1
                    continue
                else:
                    break
            return ret

        # term -> item | item term
        def term() -> set:
            nonlocal idx
            # Initialize an empty set and take its Cartesian product with subsequent results
            ret = {""}
            # An item starts with { or a lowercase letter; continue matching only when this condition is met
            while idx < n and (
                expression[idx] == "{" or is_letter(expression[idx])
            ):
                sub = item()
                tmp = set()
                for left in ret:
                    for right in sub:
                        tmp.add(left + right)
                ret = tmp
            return ret

        # item -> letter | { expr }
        def item() -> set:
            nonlocal idx
            ret = set()
            if expression[idx] == "{":
                idx += 1
                ret = expr()
            else:
                ret = {expression[idx]}
            idx += 1
            return ret

        ret = expr()
        return sorted(list(ret))
