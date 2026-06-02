class Solution:
    def findThePrefixCommonArray(self, A: list, B: list) -> list:
        n = len(A)
        prefix_common_array = [0] * n

        # Loop through each index to calculate common elements for each prefix
        for current_index in range(n):
            common_count = 0

            # Compare elements in A and B within the range of current prefix
            for a_index in range(current_index + 1):
                for b_index in range(current_index + 1):

                    # Check if elements match, and count if they do
                    if A[a_index] == B[b_index]:
                        common_count += 1
                        break  # Prevent counting duplicates

            # Store the count of common elements for the current prefix
            prefix_common_array[current_index] = common_count

        # Return the final list with counts of common elements in each prefix
        return prefix_common_array
