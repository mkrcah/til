## Tips on designing aggregates

- Use EventStorming Process Modelling or Software Design as a collaboration foundation
- Alberto keeps "aggregate" for historical reasons. Even Eric Evans recommends to adhere to the key message behind DDD instead of the tactics.
- Don't focus on aggregate name or nouns; focus on commands that needs to be executed on an "aggregate"
- Look for open-close symmetries in commands ("Cancel reservation" next to "Place reservation")
- Look for cause-and-effect symetries ("Reserve seat" command produces "Seat reserved" event)
- Focus on ReadModels that commands require, could be IDs of other aggregates only
- The name of an aggregate/component will emerge out of it (complex cynefin domain?)

On transactional vs. eventual consistency, Vaughn Vernon recommends:

>  When examining the use case (or story),
ask whether it's the job of the user executing the use case to
make the data consistent. If it is, try to make it transaction-
ally consistent, but only by adhering to the other rules of
aggregate. If it is another user's job, or the job of the system, 
allow it to be eventually consistent.
> — Vaughn Vernon

Fantastic resources:
- [No, you don't need to access my data - Alberto Brandolini - DDD Europe 2021](https://www.youtube.com/watch?v=gU-p90-EYSY)
- [Alberto Brandolini - 100k stickies later](https://youtu.be/fGm62ra_mQ8?si=RcA_b99vgXcm1e-d&t=1737)
- [Vaughn's papers on aggregates](https://www.dddcommunity.org/library/vernon_2011/) 
- [Eric Evans - Keynote: DDD Isn't Done: A Skeptical, Optimistic, Pragmatic Look](https://youtu.be/R2IAgnpkBck?si=w6IyvQYBs_IFC6-6&t=430)