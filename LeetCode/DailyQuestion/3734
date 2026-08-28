class Solution:
    def lexPalindromicPermutation(self, s: str, target: str) -> str:
        n = len(s)
        # Special case: length of 1
        if n == 1:
            return s if s > target else ""

        # Count the frequency of each character
        cnt = [0] * 26
        for c in s:
            cnt[ord(c) - ord("a")] += 1

        # Check if it can form a palindrome and record the characters with odd occurrences
        odd_char = ""
        for i in range(26):
            if cnt[i] % 2 == 1:
                # More than one character appears an odd number of times, cannot form a palindrome
                if odd_char != "":
                    return ""
                odd_char = chr(ord("a") + i)
            cnt[
                i
            ] //= 2  # It takes only half the characters to construct the left half

        prefix = []

        def check(c):
            left = prefix.copy()
            left.append(c)
            for i in range(25, -1, -1):
                left.extend([chr(ord("a") + i)] * cnt[i])

            palindrome = left + [odd_char] + left[::-1]

            return "".join(palindrome) > target

        # Construct the left part of each digit greedily
        for i in range(n // 2):
            found = False
            # Try to place the smallest character in lexicographical order
            for j in range(26):
                if cnt[j] == 0:
                    continue

                cnt[j] -= 1
                if check(chr(ord("a") + j)):
                    # If the constructed palindrome is greater than target, choose the character
                    prefix.append(chr(ord("a") + j))
                    found = True
                    break
                else:
                    cnt[j] += 1  # Not meeting the conditions, reset the counter
            if not found:
                return ""  # Cannot construct a palindrome larger than target

            if prefix[i] > target[i]:  # prefix is already greater than target
                left = prefix[:]
                for j in range(26):
                    left.extend([chr(ord("a") + j)] * cnt[j])
                palindrome = left + [odd_char] + left[::-1]
                return "".join(palindrome)

        # Construct the final palindrome string
        ans = prefix + [odd_char] + prefix[::-1]
        return "".join(ans)
