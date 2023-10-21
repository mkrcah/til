## Sample data and invocations with rich comments

It turns out that Clojure has an interesting type
of comments called _rich comments_, provided by the `comment` macro.

Rich comments are forms—they need to have correct syntax—
but they yield nil. They are geared towards
REPL-driven development where a developer can provide 
sample data or invocations.

For real-life Clojure examples, check:
- the bottom of the [set.clj](https://github.com/clojure/clojure/blob/master/src/clj/clojure/set.clj)
- the bottom of the [shell.clj](https://github.com/clojure/clojure/blob/master/src/clj/clojure/java/shell.clj)

For my use-case, I'm writing a small script and had
multiple sample invocations commented out and scattered 
in the file. With the `comment` macro, I can uncomment
them and use REPL for evaluation:

```clojure
(comment

  (run-tests)

  (do
    (def TILS-DIR "projects/til")
    (get-all-tils TILS-DIR))
  
  (->til-slug {:topic "clojure" :header "hello  `test` "})

  (new-til? (io/file "clojure/new-til.md")))
```

Some rules of thumbs about rich comments:
- they typically live at the bottom of the file
- they can contain things not yet done
- you can put multiple statements in a `do` form, to execute them all at once 


Further reading:
- https://youtu.be/Qx0-pViyIDU?si=5-3Zjg8RycQILXNv&t=1185
- https://betweentwoparens.com/blog/rich-comment-blocks/
- https://clojuredocs.org/clojure.core/comment
