class Solution:
    def longestSubarray(self, nums, limit):
        max_heap = []
        min_heap = []

        left = 0
        max_length = 0

        for right in range(len(nums)):
            heapq.heappush(max_heap, (-nums[right], right))
            heapq.heappush(min_heap, (nums[right], right))

            # Check if the absolute difference between the maximum and minimum values in the current window exceeds the limit
            while -max_heap[0][0] - min_heap[0][0] > limit:
                # Move the left pointer to the right until the condition is satisfied.
                # This ensures we remove the element causing the violation
                left = min(max_heap[0][1], min_heap[0][1]) + 1

                # Remove elements from the heaps that are outside the current window
                while max_heap[0][1] < left:
                    heapq.heappop(max_heap)
                while min_heap[0][1] < left:
                    heapq.heappop(min_heap)

            # Update max_length with the length of the current valid window
            max_length = max(max_length, right - left + 1)

        return max_length
