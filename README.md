# TypeErasure
definite guide to c++ type erasure technique

## Use case

Classic use case for type erasure would be need to fill the container with elements of different types, which by itself is 
cahllange cause, std containers, for example std::vector by its declaration requests to define underlying element type.
Naive solution would be to declare container of a pointers to base class, and we would be able to fill the container
with pointers to base class initialized with pointers to any of the derived classes pointers. 
Further, using polimorphism, elements would behave in order to execute derived type overided virtual functions.
This approach has many issues related to various aspects, as many would expect, I wouldn't put on first place performance issues,
eventhugh there are menay, but such an implementation makes itself not easy to understand in a any use case more complex than basic one,
also, it does not respect any of SOLID or DRY principles.

#Solution with combination of Strategy Pimpl design patterns with Value semantics 
