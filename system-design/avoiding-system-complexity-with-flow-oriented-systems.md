## Avoiding system complexity with flow-oriented systems

In the talk [The language of a system](https://www.youtube.com/watch?v=ROor6_NGIWU), 
Rich Hickey suggests to build systems following a metaphor of a production line /  
flow-oriented programming, as opposed to place-oriented programming and object-oriented programming.  

In a production line we have four things:

- transforming (values)
- moving (values)
- routing (values)
- remembering (values)

Rich recommends to write code such that we keep these four things as much separate as possible, 
and don't mix it; to encourage reuse and composition. 

Some details he mentions:
- moving and remembering is not purely functionaly, but we need a way to interact with the world  
- remembering is not incompatible with functional programming; as compared to updating in place (see atoms, refs, agents, Datomic)
- for moving, try to decouple consumer from producer both in identity and availability (queues, pub/sub)
