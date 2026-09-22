# Chapter 12: I Need to Make Many Changes in One Area. Do I Have to Break Dependencies for All the Classes Involved?
- Instead of getting every class under test, test "one level back" at a spot that covers all your changes
- **Interception point** - a point in your program where you can detect the effects of a particular change
  - Closer to the change is better
- **Pinch point** - a narrowing in an effect sketch, a place where tests against a couple of methods can detect changes in many methods
  - Depends on what you're changing
  - Often a sign of good encapsulation
- Pinch point tests are temporary: use them to refactor safely, then replace them with unit tests