class Solution:
    def getHappyString(self, n: int, k: int) -> str:
        current_string = ""
        happy_strings = []
        # Generate all happy strings of length n
        self.generate_happy_strings(n, current_string, happy_strings)

        # Check if there are at least k happy strings
        if len(happy_strings) < k:
            return ""

        return happy_strings[k - 1]

    def generate_happy_strings(
        self, n: int, current_string: str, happy_strings: list
    ):
        # If the current string has reached the desired length, add it to the list
        if len(current_string) == n:
            happy_strings.append(current_string)
            return

        # Try adding each character ('a', 'b', 'c') to the current string
        for current_char in ["a", "b", "c"]:
            # Skip if the current character is the same as the last character
            if len(current_string) > 0 and current_string[-1] == current_char:
                continue

            # Recursively generate the next character
            self.generate_happy_strings(
                n, current_string + current_char, happy_strings
            )
