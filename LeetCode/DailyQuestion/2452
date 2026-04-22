class TrieNode:
    def __init__(self):
        self.child = [None] * 26
        self.isEnd = False


class Solution:
    def __init__(self):
        self.root = TrieNode()

    def insert(self, word):
        node = self.root
        for c in word:
            idx = ord(c) - ord("a")
            if not node.child[idx]:
                node.child[idx] = TrieNode()
            node = node.child[idx]
        node.isEnd = True

    def dfs(self, word, i, node, cnt):
        if cnt > 2 or not node:
            return False

        if i == len(word):
            return node.isEnd

        idx = ord(word[i]) - ord("a")

        # no changes made
        if node.child[idx] and self.dfs(word, i + 1, node.child[idx], cnt):
            return True

        # made changes
        if cnt < 2:
            for c in range(26):
                if c == idx:
                    continue
                if node.child[c] and self.dfs(
                    word, i + 1, node.child[c], cnt + 1
                ):
                    return True

        return False

    def twoEditWords(self, queries, dictionary):
        for w in dictionary:
            self.insert(w)

        res = []
        for q in queries:
            if self.dfs(q, 0, self.root, 0):
                res.append(q)
        return res
