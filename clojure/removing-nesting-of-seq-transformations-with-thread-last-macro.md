## Removing nesting of seq transformations with thread-last macro

When doing multiple transformations on a sequence, the code
might lead to nesting which might harm readability.

```clojure
(defn get-all-tils []
  (map #(.getAbsolutePath %)
       (filter #(not= (.getName %) "README.md")
        (filter #(str/ends-with? (.getName %) ".md")
               (file-seq tils-dir)))))

```

It turns out that sequence functions take the sequence as the **last** argument,
and there's syntactic sugar in form of thread-last macro that could simplify such transformations:

```clojure
(defn get-all-tils []
  (->> (file-seq tils-dir)
       (filter #(str/ends-with? (.getName %) ".md"))
       (filter #(not= (.getName %) "README.md"))
       (map #(.getAbsolutePath %))))
```

More reading: https://stuartsierra.com/2018/07/06/threading-with-style