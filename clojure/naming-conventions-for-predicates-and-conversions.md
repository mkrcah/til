## Naming conventions for predicates and conversions

It turns out that Clojure has naming conventions 
for predicates and conversion functions: predicates 
should end with `?`, and conversions should 
use `->` in the name.

Some examples:

From Metabase codebase:
```clojure
; metabase codebase
(defn- env->DataSource
  [db-type {:keys [mb-db-connection-uri mb-db-user mb-db-pass], :as env-vars}]
  (if mb-db-connection-uri
    (mdb.data-source/raw-connection-string->DataSource mb-db-connection-uri mb-db-user mb-db-pass)
    (mdb.data-source/broken-out-details->DataSource db-type (broken-out-details db-type env-vars))))
```

From camel-case conversions:
```clojure
(require '[camel-snake-kebab.core :as csk])

(csk/->camelCase 'flux-capacitor)
; => 'fluxCapacitor

(csk/->SCREAMING_SNAKE_CASE "I am constant")
; => "I_AM_CONSTANT"
```

From [Clojure style-guide](https://guide.clojure.style/#naming-conversion-functions):
```clojure
;; good
(defn f->c ...)

;; not so good
(defn f-to-c ...)

;; good
(defn palindrome? ...)

;; bad
(defn palindrome-p ...) ; Common Lisp style
(defn is-palindrome ...) ; Java style
```



 