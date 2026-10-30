

## Project: Word Ladder

```python
wordlist = ["cat", "cot", "cog", "dog", "bat", "cut", "dot", "dig"]

# START Represint the Graph
def diff(w1, w2):
    if len(w1) != len(w2):
        return False
    counter = 0
    for index in range(len(w1)):
        if w1[index] != w2[index]:
            counter += 1
    return counter == 1

def adj_list():
    list_represint = {}
    for w in wordlist:
        list_represint[w] = []

    for f_word in wordlist:
        for s_word in wordlist:
            if diff(f_word, s_word):
                list_represint[f_word].append(s_word)
    return list_represint
# END Represint the Graph


# START Solve
def bfs(garph, s_word, e_word):
    if (not garph.get(s_word)) or (not garph.get(e_word)):
        return "First Word is Not Found"
    queue = [s_word]
    parent = {s_word: None}
    while len(queue) > 0:
        current = queue.pop(0)
        if current == e_word:
            path = []
            word_backtarck = e_word
            while word_backtarck is not None:
                path.append(word_backtarck)
                word_backtarck  = parent[word_backtarck]
            path.reverse()
            return path
        for neg in garph[current]:
            if neg not in parent:
                parent[neg] = current
                queue.append(neg)
    return "Not Fount"
# END Solve




# STAR MAIN
s_word = input("Enter the First Word: ")
e_word = input("Enter the Secind Word: ")
garph = adj_list()
print(bfs(garph, s_word, e_word))
# END MAIN


```