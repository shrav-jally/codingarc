class Solution:
    def countCompleteComponents(self, n: int, edges: List[List[int]]) -> int:
        # Adjacency lists for each vertex
        graph = [[] for _ in range(n)]
        # Map to store frequency of each unique adjacency list
        component_freq = defaultdict(int)

        # Initialize adjacency lists with self-loops
        for vertex in range(n):
            graph[vertex] = [vertex]

        # Build adjacency lists from edges
        for v1, v2 in edges:
            graph[v1].append(v2)
            graph[v2].append(v1)

        # Count frequency of each unique adjacency pattern
        for vertex in range(n):
            neighbors = tuple(sorted(graph[vertex]))
            component_freq[neighbors] += 1

        # Count complete components where size equals frequency
        return sum(
            1
            for neighbors, freq in component_freq.items()
            if len(neighbors) == freq
        )
