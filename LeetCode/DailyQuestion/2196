class Solution:
    def createBinaryTree(
        self, descriptions: List[List[int]]
    ) -> Optional[TreeNode]:
        # Sets to track unique children and parents
        children = set()
        parents = set()
        # Dictionary to store parent to children relationships
        parentToChildren = {}

        # Build graph from parent to child, and add nodes to sets
        for d in descriptions:
            parent, child, isLeft = d
            parents.add(parent)
            parents.add(child)
            children.add(child)
            if parent not in parentToChildren:
                parentToChildren[parent] = []
            parentToChildren[parent].append((child, isLeft))

        # Find the root node by checking which node is
        # in parents but not in children
        for parent in parents.copy():
            if parent in children:
                parents.remove(parent)

        root = TreeNode(next(iter(parents)))

        # Starting from root, use BFS to construct binary tree
        queue = deque([root])

        while queue:
            parent = queue.popleft()
            # Iterate over children of current parent
            for childValue, isLeft in parentToChildren.get(parent.val, []):
                child = TreeNode(childValue)
                queue.append(child)
                # Attach child node to its parent based on isLeft flag
                if isLeft == 1:
                    parent.left = child
                else:
                    parent.right = child

        return root
