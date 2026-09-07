# Chapter 6
- Tests make for better code
- Changes become easier
- Programming becomes less frustrating
- it takes time to get over the testing hump

## Methods
- **Sprout Method** - when you need to add a feature, write the code in a new method
    1. Identify where you need to make your code change
    2. If the change can be formulated as a single sequence of statements in one place in a method, write down a call for a new method that will do the work involved and then comment it out
    3. Determine what local variables you need from the source method, and make them arguments to the call
    4. Determine whether the sprout method will need to return values to source method. If so, change the call so that its return value is assigned to a variable
    5. Develop the sprout method using TDD
    6. Remove the comment in the source method to enable the call
- **Sprout Class** - same concept as a sprout method but a class instead
    1. Identify where you need to make your code change
    2. If the change can be formulated as a single sequence of statements in one place in a method, think of a good name for a class that could do that work. Afterward, write code that would create an object of that class in that place, and call a method in it that will do the work that you need to do; then comment those lines out.
    3. Determine what local variables you need from the source method, and make them arguments to the classes' constructor
    4. Determine whether the sprouted class will need to return values to the source method. If so, provide a method in the class that will supply those values, and add a call in the source method to receive those values
    5. Develop the sprout class test first
    6. Remove the comment in the source method to enable the object creation and calls
- **Wrap Method**
    - **V1** - creating a method with the name of the original method
        1. Identify a method you need to change
        2. If the change can be formulated as a single sequence of statements in one place, rename the method and then create a new method with the same name and signature as the old method.
        3. Place a call to the old method in the new method
        4. Develop a method for the new feature, test first, and call it from the new method
    - **V2** - Adding a new method
        1. Identify a method you need to change
        2. If the change can be formulated as a signle sequence of statements in one place, develop a new method for it using TDD
        3. Create another method that calls the new method and the old method
- **Wrap Class**
    1. Identify a method where you need to make a change
    2. If the change can be formulated as a sigle sequence of statements in one place, create a class that accepts the class you are going to wrap as a constructor argument. 
    3. Create a method on that class, using TDD that does the new work. Write another method that calls the new method and the old method on the wrapped class
    4. Instatiate the wrapper class in your code in the place where you need to enable the new behavior.

    