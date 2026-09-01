# Chapter 4
- **Seam** - a place where you can alter behavior in your program without editing in that place 
- **Enabling Point** - Every seam has an eneabling point, a place where you can make the decision to use one behavior or another

## Different Types of Seams
- Preprocessing seams - happens before compile time (ex. #if ENV = TESTING)
- Link Seams - swapping dependency injection (ex. using an interface)
- Object seams - changing which method gets called (ex. passing an Object in as a parameter)

Seams allow you to break dependencies and test without editing the code that you are trying to test
