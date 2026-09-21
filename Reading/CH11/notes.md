# Chapter 11: I Need to Make a Change. What Methods Should I Test?
When changing code we need to know what effects that has on other pieces of code. One way to do this is by drawing effect diagrams to help us to know at a glance if I make changes here it might change here. We want to limit those effects and for the effects we need make sure we have them under test.


# Chapter 11: I Need to Make a Change. What Methods Should I Test?
When changing code we need to know what effects that has on other pieces of code. One way to do this is by drawing effect diagrams to help us to know at a glance if I make changes here it might change here. We want to limit those effects and for the effects we need make sure we have them under test.

## Two directions of reasoning
- **Backward (effect sketching from a point in code):** given a class/method, figure out everything that could cause its results to change.
- **Forward (from a change point):** given a place you're about to change, trace what it could affect downstream, all the way out to what a caller can observe.
- Also check superclasses/subclasses — protected/package-scoped state can be touched by a subclass in ways your sketch of the single class won't show.

## The heuristic (from the book)
1. Identify a method that will change.
2. If it has a return value, look at its callers.
3. If it modifies values, look at the methods that use those values, and the methods that use those methods.
4. Check superclasses/subclasses that might use those instance variables/methods.
5. Check parameters — are they or their return values used elsewhere by the code you want to change?
6. Check global/static data modified anywhere in the methods you've identified.

## Three ways effects propagate
1. Return values used by a caller.
2. Modification of objects passed as parameters, used later.
3. Modification of static/global data, used later — the sneakiest one, since it won't show up in a method's signature.

## Know your language
Every language has "firewalls" that stop effect propagation — knowing them means you don't have to look past them. Examples: `private` vs package-scoped fields in Java (package scope means anything in the package could be touching the field directly); `const` in C++ normally blocks mutation, but `mutable` fields quietly undo that guarantee. Don't take a keyword like `const` at face value without checking.

## Simplifying effect sketches
Removing small duplication can shrink the sketch itself. Example: `getInterface` originally duplicated declaration-lookup logic; once it calls `getDeclaration` internally instead, testing `getInterface` also exercises `getDeclaration`, collapsing the number of distinct endpoints you need to cover. Fewer endpoints = easier decisions about where to write tests.

## Effects and encapsulation
Dependency-breaking techniques often break encapsulation, and that's a real cost — encapsulation reduces the number of paths you have to follow to reason about code. But encapsulation is a tool for understanding, not an end in itself. When it conflicts with getting test coverage in place, bias toward test coverage — good tests let you reason about the code directly, and you can often claw back encapsulation later once the tests exist.