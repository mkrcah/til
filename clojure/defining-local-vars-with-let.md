## Defining local variables with let 

In the following example, `(.getName file)` is
duplicated, and it's a candidate for a local var.

```clojure
(defn new-til? [file]
  (and
    (str/starts-with? (.getName file) "new")
    (str/ends-with? (.getName file) ".md")))
```

How does one create a _local_ var in Clojure? With the `let` macro. 

`let` takes two argsuments: 
- a vector of pairs (bindings)
- and an expression where these bindings are used

The example can be refactored with `let` as follows:

```clojure
(defn new-til? [file]
  (let [file-name (.getName file)]
    (and
      (str/starts-with? file-name "new")
      (str/ends-with? file-name ".md"))))
```