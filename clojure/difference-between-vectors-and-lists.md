## Difference between vectors and lists

In Clojure, there are two sequential collections: **lists** and **vectors**

```clojure
; lists
(def files '("test.md", "README.md"))

; vectors
(def files ["test.md", "README.md"])
```

**Lists** are implemented as [linked lists](https://en.wikipedia.org/wiki/Linked_list): 
- adding to the beginning in constant, adding to the end is O(n)
- they are not indexed
- `conj` add to the list (`conj` always add elements where it can be done in O(1))
- lists can be used as stack with `peek` and `pop`

**Vectors** are implemented as [bit-partitioned vector trie](https://hypirion.com/musings/understanding-persistent-vector-pt-1):
- element can be retrieved by an index, eg `(get files 1)`
- `conj` are added at the end, new vector is created 
- `count` is O(1)

Further reading:
- https://clojure.org/guides/learn/sequential_colls
- https://hypirion.com/musings/understanding-persistent-vector-pt-1
- https://www.braveclojure.com/do-things/#Anchor-3

