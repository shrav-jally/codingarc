class Solution:
    def findRotation(
        self, mat: List[List[int]], target: List[List[int]]
    ) -> bool:
        n = len(mat)
        # at most 4 rotations
        for k in range(4):
            # rotation operation
            for i in range(n // 2):
                for j in range((n + 1) // 2):
                    (
                        mat[i][j],
                        mat[n - 1 - j][i],
                        mat[n - 1 - i][n - 1 - j],
                        mat[j][n - 1 - i],
                    ) = (
                        mat[n - 1 - j][i],
                        mat[n - 1 - i][n - 1 - j],
                        mat[j][n - 1 - i],
                        mat[i][j],
                    )

            if mat == target:
                return True
        return False
