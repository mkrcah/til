## Local unit testing with with-test macro

It turns out that in Clojure it is possible to define 
a test for a function within the same form that also contains the function definition itself. 

The `with-test` macro takes a `def` or `defn` form 
as the first argument and then any number of assertions. 

Here's an example for the doc:
```clojure
(with-test
    (defn my-function [x y]
      (+ x y))
  (is (= 4 (my-function 2 2)))
  (is (= 7 (my-function 3 4))))
```

Here's an example from a small program I'm writing, a simple sluggifier:
```clojure
(with-test
  ; func definition here
  (defn ->til-slug 
    [{:keys [topic header]}]
    (str topic "/" (csk/->kebab-case header) ".md"))
  ; first assertion
  (is (= (->til-rel-path {:topic "clojure" :header "Defining local vars"})
         "clojure/defining-local-vars.md")))
```

The tests can be run with [`(run-tests)`](https://clojure.github.io/clojure/clojure.test-api.html#clojure.test/run-tests)



Further reading:
- https://clojure.github.io/clojure/clojure.test-api.html