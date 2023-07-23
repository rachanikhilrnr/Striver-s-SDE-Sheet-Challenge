class TrieNode:
    def __init__(self):
        self.children = {}
        self.countPrefix = 0
        self.isEndWord = 0

class Trie:
    def __init__(self):
        self.root = TrieNode()

    def insert(self, word):
        curr = self.root
        for char in word:
            if char not in curr.children:
                curr.children[char] = TrieNode()
            curr = curr.children[char]
            curr.countPrefix += 1
        curr.isEndWord += 1

    def countWordsEqualTo(self, word):
        curr = self.root
        for char in word:
            if char not in curr.children:
                return 0
            curr = curr.children[char]
        return curr.isEndWord

    def countWordsStartingWith(self, word):
        curr = self.root
        for char in word:
            if char not in curr.children:
                return 0
            curr = curr.children[char]
        return curr.countPrefix

    def erase(self, word):
        curr = self.root
        if self.countWordsEqualTo(word) == 0:
            return

        for char in word:
            curr = curr.children[char]
            curr.countPrefix -= 1
        curr.isEndWord -= 1