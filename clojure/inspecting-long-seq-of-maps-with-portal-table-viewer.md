## Inspecting long seq of maps with Portal table viewer 

Having a long seq of maps, I was wondering 
how to easily see what's inside. I needed a table-like view, and nREPL
wasn't providing what I needed.

It turns out there's [Portal](https://github.com/djblue/portal). 
It's perhaps best to see it in action, see resources below. 

To get the Portal up and Running for Babashka, I added the following. 
Once setup, I went to the Portal and selected the Table viewer. 

```clojure
(comment
  ; kick-off the portal
  (do
    (deps/add-deps '{:deps {djblue/portal {:mvn/version "0.9.0"}}})
    (require '[portal.api :as p])
    (p/open)
    (add-tap #'p/submit))
  
  ; send seq of lists to be visualized
  (tap> (->> raw-tx
             (take 10))))
```

Further resources:
- https://www.youtube.com/watch?v=A-QvUw5LLVU
- https://www.youtube.com/watch?v=Tj-iyDo3bq0
