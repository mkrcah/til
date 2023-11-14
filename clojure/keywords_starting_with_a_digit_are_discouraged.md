## Keywords starting with a digit are discouraged

It turns out it is recommended not to use keywords that start with a digit, such as `:2023-12-07`.

From Clojure doc: 

> The reader page defines keywords as "like symbols" and symbols 
> "begin with a non-numeric character" so the original intent was that 
> :1 would be invalid. In fact, the only reason it is readable at all is 
> due to a bug in the keyword regex.

> In general, it’s best to avoid using keywords that start with a number unless it is in a narrow and controlled scope.

If performance is a problem, then keywords might be considered.


> Keywords are cached and interned. This means that a keyword is reused 
> (reducing memory) everywhere in your program and that checks for equality 
> really become checks for identity (which are fast). 
> Additionally, keywords are invokable to look themselves up in a 
> map and thus this enables the common pattern of extracting a 
> particular field from a collection of maps possible.

Further reading:
- https://clojure.org/guides/faq#keyword_number