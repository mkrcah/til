## Change is not a thing, it's either growth or breakage

In the fantastic talk [Spec-ulation](https://www.youtube.com/watch?v=oyLBGkS5ICk), Rich Hickey mentions 
that change is not a thing, it's either **growth** or **breakage**. 

**Growth** - growing your software:
- software **provides more** (accretion)
- software **requires less** (relaxation)
- software **works better** (fixation, fixing)

**Breakage** - breaking your software:
- software **requires more**
- software **provides less**
- software has **unrelated stuff under same name**

Example:
- Adding a required function parameter is breakage
- Adding another function is growth

Rich advocates that breaking changes are **broken**, particularly so in the context of 
clients that are not in our control. We should avoid **breakage** by turning it into **accretion**, where old and new can co-exist (Java, Unix, Git, Maven).

It seems to me the concept of growth/breakage can be applied to microservices as well.
Assuming a microservice grows and doesn't break, we can safely deploy the latest version
in isolation without considering other microservices. 