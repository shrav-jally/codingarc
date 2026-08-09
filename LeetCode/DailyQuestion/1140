class Solution:
    def stoneGameII(self, piles: List[int]) -> int:
        # Initialize the memoization table
        memo = [[0] * len(piles) for _ in range(len(piles))]
        # Initialize the suffixSum array
        suffix_sum = piles[:]

        # Compute the suffix sums
        for i in range(len(suffix_sum) - 2, -1, -1):
            suffix_sum[i] += suffix_sum[i + 1]

        # Call the recursive function to find the maximum stones Alex can collect
        return self.max_stones(suffix_sum, 1, 0, memo)

    def max_stones(
        self,
        suffix_sum: List[int],
        max_till_now: int,
        curr_index: int,
        memo: List[List[int]],
    ) -> int:
        # If the current index plus twice the maxTillNow exceeds the array size, take all remaining stones
        if curr_index + 2 * max_till_now >= len(suffix_sum):
            return suffix_sum[curr_index]

        # Return the memoized result if it exists
        if memo[curr_index][max_till_now] > 0:
            return memo[curr_index][max_till_now]

        # Initialize the result to a very large number (infinity)
        res = float("inf")

        # Iterate through possible moves and calculate the minimum result for the opponent
        for i in range(1, 2 * max_till_now + 1):
            res = min(
                res,
                self.max_stones(
                    suffix_sum,
                    max(i, max_till_now),
                    curr_index + i,
                    memo,
                ),
            )

        # Memoize the result as the current suffix sum minus the opponent's best outcome
        memo[curr_index][max_till_now] = suffix_sum[curr_index] - res
        return memo[curr_index][max_till_now]
