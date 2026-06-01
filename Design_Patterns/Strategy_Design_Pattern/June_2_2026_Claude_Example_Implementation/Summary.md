Yeah so First things first
Strategy pattern is to unify the behaviour 
Factory pattern is to unify the creation

Factory pattern chokes if the construction parameters are increasing everytime
We are using Factory pattern to have the creation facade at one place simple and just one user parameter is governing what to create rather than any complicated logic simple

Factory pattern's elaborated brother is Builder Pattern which we'll see soon
Other alternate to Factory pattern being using DI framework and instantiate the required objects only once and business logic remains independent of every object 


Claude's Response
1. "Strategy unifies behaviour, Factory unifies creation." Nice parallel, keep it — just sharpen the verb. Strategy doesn't unify behaviour so much as make it swappable behind one interface. What gets unified is the access point (one interface); the behaviour behind it varies. Same shape for Factory: one access point for creation, varying concretes behind it. Both = "one stable surface, many things behind it." Good instinct, just don't think of it as merging behaviours.
2. "creation facade." Careful with that word — Facade is its own named pattern (a simplified front over a complex subsystem). What you mean here is a single chokepoint / entry point for creation. Different beast; don't let the word cross-wire when you meet the real Facade later.
3. "Builder is Factory's elaborated brother." This is the one real correction. Builder is not a fancier Factory — it's a sibling creational pattern solving a different pain: the param-explosion you hit. Factory answers "which class do I instantiate?"; Builder answers "this one class is miserable to construct, let me do it step by step." They even team up (a factory can use a builder inside it). The actual "elaborated brother" of your simple factory, in GoF terms, is Factory Method / Abstract Factory — park those names for later.
4. "DI is an alternate to Factory, instantiate once." Refine both halves. DI isn't really an alternative — it's the same push-to-the-edge idea taken to its architectural conclusion. And the essence isn't "instantiate once" (that's a lifecycle/scope detail) — it's "business logic never constructs; it receives." All the news live at the composition root; everything else just gets handed what it needs.
