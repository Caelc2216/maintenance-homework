# Chapter 9

Four most common problems we encounter:
1. Objects of the class can't be created easily
2. The test harness won't easily build with the class in it
3. The constructor we need to use has bad side effects
4. Significant work happens in the constructor, and we need to sense it

Start with a construction test: just try to instantiate the class, no assertions. Let the errors tell you what's actually blocking you.

## Techniques

**Pass Null** - Consider passing null in as all of the parameters to see which parameters you really need in a test

**Extract Interface** - Pull the methods you actually need off a troublesome class into an interface, then write a fake class that implements it

**Parameterize Constructor** - Move a dependency that's created inside the constructor out to a constructor parameter instead

**Supersede Instance Variable** - Add a setter that swaps an internal field after construction, once you're past a hard-to-reach dependency in a constructor

**Extract and Override Factory Method** - Override the method that creates an internal object, in a test subclass

**Introduce Static Setter** - For singletons, add a static method that lets tests swap in a fake or test instance

**Subclass and Override Method** - Override just the one problematic method in a throwaway test subclass, rather than extracting a whole interface
