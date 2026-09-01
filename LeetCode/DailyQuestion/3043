class Solution:
    def longestCommonPrefix(self, arr1, arr2):
        arr1_prefixes = set()  # Set to store all prefixes from arr1

        # Step 1: Build all possible prefixes from arr1
        for val in arr1:
            while val not in arr1_prefixes and val > 0:
                # Insert current value as a prefix
                arr1_prefixes.add(val)
                # Generate the next shorter prefix by removing the last digit
                val //= 10

        longest_prefix = 0

        # Step 2: Check each number in arr2 for the longest matching prefix
        for val in arr2:
            while val not in arr1_prefixes and val > 0:
                # Reduce val by removing the last digit if not found in the prefix set
                val //= 10
            if val > 0:
                # Length of the matched prefix using log10 to determine the number of digits
                longest_prefix = max(longest_prefix, len(str(val)))

        return longest_prefix
