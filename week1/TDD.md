# Test-drive a simple program using objects and methods
This week I have to learn how to test-drive a simple program.<br />
I have started on this during the Boris-bikes challenge.<br />
I had to use TDD to develop the objects:
- Person
- Bike
- DockingStation

These had to include methods such as:
- .working?
- .release
- .dock_bike

## I need to deepen my understanding of TDD.<br />

In order to do this I will:
1. Start with this [exercise](https://github.com/makersacademy/skills-workshops/blob/master/practicals/test_driving.md)
2. Rubber duck my code so far on Boris bikes.
3. Then try and explain it to a senior or coach and ask for feedback.

## TDD workshop notes

### Why do we do TDD?

- To make sure our code does what we want it to do by checking the program does what we actually expect it to.
- Also to ensure our software doesn't do things we don't want it to do.
- The process forces us to think more deeply about what is really required by our users.
- Having the tests in place ensures when we update, maintain and add new features to our program in the future, that we can easily check the old functionality is still working.

### Why do we write the tests first?

- Writing the tests first is a method of conciously designing our program to fit user needs.
- Testing is about WHAT the program does.
- Programming is about HOW the program does it.
- By writing the tests first, we first decided and clarify what we actually need to program to do. Then we can write the simplest possible to program to suit those needs.
- This prevents over-engineering and the creation of fancy code, that doesn't actually provide the users with what they want.
- Overall it makes sure we write a program for the users, and not for just for ourselves. 

### Feature and unit tests

- A feature test is a desinged based on user requirements. The test is written from the point of view of a user, and what feature they need implementing. The test writer writes a tests to check that the feature works.
- A unit test simply checks a small peice of code is working.
- We always write the feature test first, then we write unit tests until the feature test is passed.
- This ensures we don't over engineer the problem, but instead we write the minimum code to make the feature work.

### The TDD Cycle

- RED-GREEN-REFACTOR