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

The build method doesn't create the actual object but instead uses `.new`

*  Often, when I create an action object I try to separate initialization, execution, and saving the result.
* One reason to separate these features is that it is much easier to write fast tests of using the workflow object if I can do so without hitting the database.jj:w
 
> **Prescription 9:** Use `:aggregate_failures` to get the best features of single-assertion and multiple-assertion tests

Controller tests, which have been a feature of Rails from the beginning, have increasingly been seen as lower value tests in a couple of different ways.

* Controller tests can feel like duplicates of integration tests
* With workflow objects, the controller doesn't have much left to do


# Chapter 4: What Makes Great Tests

> **Prescription 10:** Your tests are also code. Specifically, your tests are code that does not have tests.

Invoking `it` methods inside a look is a **bad idea**.

Steps you can take to minimize the costs of tests and maximize the value:

* Instead of thinking about what will make a test pass, think about what will make it fail. If there's no way to make the test fail that won't make an already existing test fail, maybe you don't need the test.
* Think of integration tests that will help you atomate a series of actions that are useful while developing the code, so you get time savings from running the integration test.
* For unit tests, write the test so that it invokes the minimal amount of code needed to make the test fail.
* Try to avoid high-cost activities like calling external libraries and saving a lot of objects to a database. A good way to avoid this is to use test doubles to prevent unit tests from having to use real dependencies.
* If you find a single bug that makes multiple tests fail, think about whether all those tests are needed. If the failure is in setup, think about whether all those tests need all that setup.
* Sometimes tests that are useful duing development are completely superseded by later tests. These tests can be deleted.
* If it takes a lot of setup to write a unit test, consider the possibility that the test is trying to tell you that the design of the code could be improved to minimize dependencies.

> **Prescription 11:** Think about both the short-term and long-term costs of tests as you write them.

### SWIFT: The Five Qualities of Valuable Tests

SWIFT stands for:

* Straightforward
	* Naming tests is critical to being straightforward
* Well-defined
	* A test is well-defined if running the same test repeatedly gives the same result.
	* If your tests are not well-defined, the symptom will be intermittent, seemingly random test failures
	* Three classic causes of repeatability problems are:
		* Time and date testing
		* Random numbers
		* Third-party or Ajax calls
* Independent
	* A test is independent if it does not depend on any other tests or external data to run
	* An independent test suite gives the same results no matter the order in which the tests are run
* Fast
	* Speeding tests up often means isolating application logic from the Rails stack so that logic can be tested without loading the entire Rails stack or without retreiving test data from the database.
* Truthful
	* A truthful test accurately reflects the underlying code - it passes when the underlying code works, and fails when it does not.
	* A frequent cause of brittle tests is targeting assertions at surface features that might change even if the underlying logic stays the same. The classic example along these lines is view testing, in which you base the assertion on the creative text on the page (which will frequently change even though the basic logic stays the same)

# Chapter 5: Testing Models


### A TDD Metaprocess

> **Prescription 12:** If you find yourself writing tests that already pass given the current state of the code, that often means you're writing too much code in each pass.

### Refactoring Models

> **Prescription 13:** Refactoring is where a lot of design happens in TDD, and it's easiest to do in small steps. Skip it at your peril.

At the most abstract level, you're looking for three things:

1. Complexity to break up
2. Duplication to combine
3. Abstractions waiting to be born

#### Break up Complexity

Booleans, local variables, and inline comments are almost always candidates for extraction.

* Any compound Boolean logic expression goes in its own method. Give people reading your code a fighting chance by hiding the expression behind a name that expresses the code’s intent, such as valid_name? or has_purchased_before?
* Local variables are relatively easy to break out into methods with the same name as the variable. You'll be surprised at how much more flexible your code feels if you minimize the number of local variables in methods.
* In long methods, sometimes a single-line comment breaks up the method by describing what the next part does. This nearly always is better extracted to a separate method with a name based on the comment's contents.

> **Prescription 14:** Try to extract methods when you see compound Booleans, local variables, or inline comments.

#### Combine Duplication

You need to look out for three kinds of duplication:

* Duplication of fact
	* The key metric is how many places in the code would need to change if the underlying fact changed, with the ideal number being "one"
* Duplication of logic
* Duplication of structure
	* Means there's a missing abstraction, which in Ruby generally means you can move some code into a new class. One symptom is a set of instance attributes that are always used together - especially if the same group of attributes is being passed to multiple methods.
	* When you break out related attributes into their own class, as in the Name example, you'll often find it's much easier to add complexity when you have a dedicated place for that logic. You'll also find that these small classes are easy to test because Name no longer has a dependency on the database or any other code.
	* Once you've separated functionality into separate classes, an object-oriented program is supposed to switch based on class, using message passing and polymorphism

```ruby
def calculator
  if complete?
    CompleteTaskCalculator.new(self)
  else
    IncompleteTaskCalculator.new(self)
  end
end

def calculate
  calculator.calculate_time
end
```

> **Prescription 15:** Expectations that cover different branches of the application logic should be handled in separate specs



#### Testing ActiveRecord Finders

> Being able to compose and chain finder methods is awesome. But finder methods occupy an awkward place between methods you might write and Rails core features, leading to the question of how best to test them.

Here are some guidelines:

* Be aggressive about extracting compound finder statements to their own method. When using test doubles, having finders called behind other methods makes it much easier to avoid touching the database when you don't need to.
* Don't shy away from creating ActiveRecord objects when you are legitimately teesting database retrieval behavior, but don't create more objects than you need to.
* If you are testing a method that finds objects based on criteria, start with a test that creates two objects. That's one object you expect the method to find and one that you do not, which allows you to cover the logic from both sides:

	```ruby	it "finds completed tasks" do		complete = Task.create(completed_at: 1.day.ago, title: "Completed")
		incomplete = Task.create(completed_at: nil, title: "Not Completed")
		expect(Task.complete).to match([an_object_having_attributes(title: "Completed")])	end
	```

#### Testing Shared Modules and ActiveSupport Concerns

> Often you’ll have multiple models in your application that share some kind of common feature set. For example, you may have multiple object types that can be purchased, tagged, or commented on. You can use standard Ruby classes and modules for this shared behavior. If the shared behavior has both class and instance methods, Rails provides `ActiveSupport::Concern`, which allows you to easily use a common pattern to mix multiple kinds of behavior from one module.

Testing this shared behavior can be a challenge. RSpec has a powerful mechanism for sharing specs across multiple objects that have common functionality, simply called the **shared example**

#### Writing Your Own RSpec Matchers

```ruby
RSpec::Matchers.define :be_of_size do |expected|
  match do |actual|
    actual.size == expected
  end
end
```

> The definition starts with a call to RSpec::Matchers.define, passing it the name of the matcher and a block. The block takes an argument that will eventually be the expected value—the value passed to the matcher when called.

There is then a line in `rails_helper.rb` that you can uncomment to have the entire `spec/support` directory loaded automatically.

# Chapter 6: Adding Data to Tests