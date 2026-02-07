class Solution:
    def minimumDeletions(self, s: str) -> int:
        b_count = 0
        deletions = 0
        
        for ch in s:
            if ch == 'b':
                b_count += 1
            else:  # ch == 'a'
                deletions = min(deletions + 1, b_count)
        
        return deletions
