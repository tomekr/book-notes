# Chapter 1

Success with TDD development starts with trusting the process. The classic process goes like this:

1. Create a test. The test should be short and test for one thing in your code. The test should run automatically.
2. Make sure the test fails. Verifying the test failure before you write code helps ensure that the test really does what you expect.
3. Write the simplest code that could possibly make the test pass. Don't worry about good code yet. Don't look ahead. Sometimes, write just enough code to clear the current error.
4. After the test passes, refactor to improve the code. Clean up. duplication. Optimize. Create new abstractions. Refactoring is a key part of design, so don't skip this. Remember to run the tests again to make sure you haven't changed any behavior.

> **Prescription 1:** Use the TDD process to create and adjust your code's design in small, incremental steps.

* Continually aligning your code to the tests tends to result in code that is made up of small methods, each of which does one thing. These methods tend to be loosely coupled and have minimal side effects. As it happens, the hallmarks of easy-to-change code include small methods that do one thing, are loosely coupled, and have minimal side effects.

> **Prescription 2:** In a test-driven process, if it is difficult to write tests for a feature, strongly consider the possibility that the design of the underlying code needs to be changed.

The kinds of tests written in a TDD process are not a substitute for acceptance testing, where users or customers verify that the code does what the user or customer expects.

The TDD process has a name for the kind of exploratory code you write while trying to figure out the needed functionality: **spike**, as in, "I don't know if we can do what we need with the Twitter API; let's spend a day working on a spike for it." When working in spike mode, TDD is generally not used, but code written during the spike is not expected to be used in production, it's just a proof of concept to be thrown away and replaced with a version written using TDD.

# Chapter 2: Test-Driven Development Basics

> **Prescription 3:** Initializing objects is a good starting place for a TDD process. Another good approach is to use the test to design what you want a successful interation of the feature to look like.

Over-reliance on implementation details is a major cause of test fragility, so when you can describe the behavior rather than the implementation, you should do so.

> **Prescription 4:** When possible, write your tests to describe your code's behavior, not its implementation


> **Prescription 5:** Keeping your code as simple as possible allows you to focus complexity on the areas that really need complexity.

> **Prescription 6:** Choose your test data and test-variable names to make it easy to diagnose failures when they happen. Meaningful names and data that doesn't overlap are helpful.

# Chapter 3: Test-Driven Rails

A good test suite consists of a few end-to-end tests, a lot of tests that target a single unit, and relatively few tests that cover an intermediate amount of code. By moving logic outside of the Rails controller and views, you can turn those harder to test parts of Rails tests into code that can be tested with faster and more robust unit tests.

Features worked on during this chapter:

* A user can create a project and seed it with initial tasks using the some-what contrived syntax of `task name:size`.
* A user can enter a task, associate it with a project, and see it on the project page.
* A user can change a task's state to mark it as done.
* A project can display its progress and status using the date projection you created in the last chapter.

We follow a testing practice called **outside-in testing**, which involves writing an end-to-end test that defines the feature (the "outside"), and then augmenting it with a series of. unit tests that drive the actual code and design ("the inside").

> **Prescription 7**: Using Capybara allows you to simulate user activity for end-to-end tests of your Rails features

> **Prescription 8**: I like placing business logic outside Rails classes. It makes that logic easier to test and manage.





