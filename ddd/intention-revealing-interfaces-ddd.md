## Design with intention-revealing interfaces (DDD)

Evans in DDD:

> If a developer must consider the implementation of a component in order to use it, the value of encapsulation is lost.  If someone other than the original developer must infer the purpose of an object or operation based on its implementation, that new developer may infer a purpose that the operation or class fulfills only by chance.  If that was not the intent, the code may work for the moment, but the conceptual basis of the design will have been corrupted, and the two developers will be working at cross-purposes.

> Name classes and operations to describe their effect and purpose, without reference to the means by which they do what they promise.  This relieves the client developer of the need to understand the internals.  The name should conform to the Ubiquitous Language so that the team members can quickly infer their meaning.


Observations:
- Surprisingly, using such naming seem to guide design. 
- Naming use-cases with their intention fits well with EventStorming and with [Atomic Architecture](https://www.juxt.pro/blog/atomic-architecture/).
- Intention-revealing interfaces seems to be an ongoing effort for deeper insight. 

Further reading:
- https://khalilstemmler.com/articles/typescript-domain-driven-design/intention-revealing-interfaces/
- https://lostechies.com/jimmybogard/2007/11/29/intention-concealing-interfaces-blob-parameters/
- [Naming in DDD - Sepehr Namdar & Khaled Souf - DDD EU 2022](https://www.youtube.com/watch?v=KHgftXIlGsY&t=300s)
- [Get to Domain Abstraction (Article 7)](https://www.digdeeproots.com/articles/naming-process/get-to-domain-abstraction/)
- [How to Improve on Naming Contexts in Domain-Driven Design](https://www.adamconrad.dev/blog/how-to-improve-on-naming-contexts-in-domain-driven-design/)