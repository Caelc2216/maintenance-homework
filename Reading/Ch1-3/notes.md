# Chapter 1: Changing Software

## Four Reasons to Change Software
1. Adding a feature
2. Fixing a bug
3. Improving the design
4. Optimizing resource usage

### Adding Features and Fixing Bugs
- People have a hard time distinguishing between a bug fix and a new feature
- Are we adding behavior or changing behavior?
- Is it possible to add behavior without changing behavior?

### Improving the Design
- Changing code to improve maintainability, while keeping the behavior intact. If the behavior changes that is often a bug
- Improving design without changing its behavior is called **refactoring**
- Refactoring should be done with tests

### Optimization
- like refactoring we don't want to change the behavior, but we want to change how we use resources, usually time or memory

## Three different things can change when we do work in a system
1. Structure
2. Functionality
3. Resource Usage

What typically changes during these four types of changes
||Adding a Feature|Fixing a Bug|Refactoring|Optimizing|
|-----|----------------|------------|-----------|----------|
|Structure|Changes|Changes|Changes|-|
|Functionality|Changes|Changes|-|-|
|Resource Usage|-|-|-|Changes|

||Adding a Feature|Fixing a Bug|Refactoring|Optimizing|
|-----|----------------|------------|-----------|----------|
|Structure|Changes|Changes|Changes|-|
|New Functionality|Changes|-|-|-|
|Functionality|-|Changes|-|-|
|Resource Usage|-|-|-|Changes|

When making a change you don't know how much behavior is at risk

## Risky Change
Questions to ask to mitigate risk
1. What changes do we have to make?
2. How will we know that we've done them correctly?
3. How will we know that we haven't broken anything?

In a good system you feel pretty calm after you'be done the initial learning and are confident in the change you are about to make.

If you don't make changes often you get rusty at it.

# Chapter 2
- **Edit and Pray** - you carefully plan the changes make sure you understand the code, then poke around to make sure you didn't break anything
- **Cover and modify** - we cover software by using tests, good tests. 

## Qualities of good unit tests
1. They run fast
2. They help us localize problems

## Not a unit test if:
1. It talks to a database
2. It communicates across a network
3. It touches the file system
4. You have to do special things to your environment (such as editing configuration files) to run it

These aren't bad tests, they have a purpose, they just run slow

**The Legacy Code Dilemma**  
When we change code, we should have tests in place. To put tests in place, we often have to change code.


## Legacy Code Change Algorithm
1. Identify change points
2. Find test points
3. Brak dependencies
4. Write tests
5. Make changes and refactor

# Chapter 3
