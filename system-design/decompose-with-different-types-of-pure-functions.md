## Decompose with different types of pure functions   

In Functional Design for Clojure podcast, they [talked about](https://clojuredesign.club/episode/098-composed-learnings/)
common types of side-effect-free functions:

- predicates (provide truth values)  
- reducers (takes two args: current intermediate state, and some value, produces a new value)
- transforms
  - conversions
  - extractors 
  - mergers 
  - decorators/enrichers/augmenters 

Some notes from the podcast:
- Reducers are a way to provide mutability-like functionality in immutable world.
- To decomplect concerns, one can write functions such that they don't mix two or more concerns. To bring the functions together, one can use a thread macro.
- IO/side-effect functions could be made simpler by removing reducing, transforming, concerns, and focusing purely on the IO. 

Some observations:
- Knowing about these types of functions could guide naming and design.
- These types of functions relate to categorization that Rich mentions in [flow-oriented programming](/system-design/avoiding-system-complexity-with-flow-oriented-systems.md)

