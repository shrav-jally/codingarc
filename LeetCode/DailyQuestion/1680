class Solution:
    def concatenatedBinary(self, n: int) -> int:
        MOD = 10**9 + 7
        result = 0
        length = 0
        
        for i in range(1, n + 1):
            # If i is power of 2, increase bit length
            if (i & (i - 1)) == 0:
                length += 1
            
            result = ((result << length) + i) % MOD
        
        return result
