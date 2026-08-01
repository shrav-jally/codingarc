class TrieNode:
    def __init__(self):
        self.children = {}
        self.min_len = float("inf")
        self.idx = float("inf")


class Trie:
    def __init__(self):
        self.root = TrieNode()

    def insert(self, s: str, idx: int):
        node = self.root
        if len(s) < node.min_len:
            node.min_len = len(s)
            node.idx = idx

        for ch in s:
            c = ch
            if c not in node.children:
                node.children[c] = TrieNode()
            node = node.children[c]

            if len(s) < node.min_len:
                node.min_len = len(s)
                node.idx = idx

    def query(self, s: str) -> int:
        node = self.root

        for ch in s:
            if ch in node.children:
                node = node.children[ch]
            else:
                break

        return node.idx


class Solution:
    def stringIndices(
        self, wordsContainer: List[str], wordsQuery: List[str]
    ) -> List[int]:
        trie = Trie()

        for i, word in enumerate(wordsContainer):
            reversed_word = word[::-1]
            trie.insert(reversed_word, i)

        res = []
        for query in wordsQuery:
            reversed_query = query[::-1]
            res.append(trie.query(reversed_query))

        return res
