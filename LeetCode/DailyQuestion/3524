class Solution:
    def resultArray(self, nums: List[int], k: int) -> List[int]:
        n = len(nums)
        result = [0] * k
        # Initial state: no elements have been processed, so no non-empty subarray exists.
        dp = [0] * k

        for i in range(n):
            ndp = [0] * k  # Current state (rolling array).

            ndp[nums[i] % k] += 1

            for r in range(k):
                ndp[(r * nums[i]) % k] += dp[r]

            dp = ndp  # Update the state.

            # Accumulate the answer.
            for r in range(k):
                result[r] += dp[r]
        return result
