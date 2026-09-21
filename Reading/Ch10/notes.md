# Chapter 10: I Can't Run This Method in a Test Harness
Common problems:
- The method might not be accessible to the test. It could be private or have some other accessibility problem
- It might be hard to call the method because it is hard to construct the parameters we need to call it
- The method might have bad side effects (modifying a db) so it is impossible to run in a test harness
- We might need to sense through some object that the method uses.


## The method is private
- try to test through a public method as this would test the way the method is actually going to be used
- Loosen the methods visavility, make it protected and then create a test only subclass

If your method is hard to test than you probably have your class doing too much and should split it up