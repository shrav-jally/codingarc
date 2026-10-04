class Solution:
    def checkValidString(self, s: str) -> bool:
        n = len(s)
        memo = [[-1] * n for _ in range(n)]
        return self.is_valid_string(0, 0, s, memo)

    def is_valid_string(self, index: int, open_count: int, s: str, memo: List[List[int]]) -> bool:
        # If reached end of the string, check if all brackets are balanced
        if index == len(s):
            return open_count == 0

        # If already computed, return memoized result
        if memo[index][open_count] != -1:
            return memo[index][open_count] == 1

        is_valid = False
        # If encountering '*', try all possibilities
        if s[index] == '*':
            is_valid |= self.is_valid_string(index + 1, open_count + 1, s, memo)  # Treat '*' as '('
            if open_count > 0:
                is_valid |= self.is_valid_string(index + 1, open_count - 1, s, memo)  # Treat '*' as ')'
            is_valid |= self.is_valid_string(index + 1, open_count, s, memo)  # Treat '*' as empty
        else:
            # Handle '(' and ')'
            if s[index] == '(':
                is_valid = self.is_valid_string(index + 1, open_count + 1, s, memo)  # Increment count for '('
            elif open_count > 0:
                is_valid = self.is_valid_string(index + 1, open_count - 1, s, memo)  # Decrement count for ')'

        # Memoize and return the result
        memo[index][open_count] = 1 if is_valid else 0
        return is_valid
