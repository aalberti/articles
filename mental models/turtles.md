#Turtles rule, all the way

Mental models help you take decisions when they fit the reality you're facing.
Many models are too simple to match enough situations.
For example, the test pyramid originally assumes that you have 3 layers (unit, service, UI).
Some adapt their test pyramid to their vocabulary, adding or renaming layers.
Anyway, as soon as your system becomes just a bit complex, the reality becomes more complex than that.
You end up with separate modules (microservices?), each having several layers.
You want to find the right tradeoff, for each test, between:
- Realism: If the test passes, the corresponding use case will pass end-to-end in production.
- Speed: you want to run billions of tests in nanoseconds.
- Coverage: you want to test every edge case, imaginable or not.
- Reliability: you want your test to fail for the reasons you test. Generally, a test is solid when it embeds few things.
- Explainability: you know why a test failed.
- And many other properties like these.
For a given category of tests of a given module, you will find the right tradeoff of good practises.
This tradeoff allows you to run tests with a range of values for each of these properties.
In the multidimensional space of tests properties, you get a bubble, corresponding to a set of practises.
If you generalize this, you will get one bubble for each test category of each module.
For these tests, you mock/stub/fake these libraries, while you want their real implementations for these modules.
For this feature, you want to smoke test the end-to-end plumbing, while randomly generating edge cases at 5000 tests per second by testing the independant sub-sub domain library.
It depends.
In a simple system, you might be able to call these bubbles of good practises unit, service, or UI tests, in a way that makes a consistent sense to you across all your modules.
In more complex systems, what you call a unit test is totally different than what you would call a unit test in that other module.

And this is where it becomes interesting: the integration testing of a system is the unit testing of a higher level one.
When you code, in any language, there is a likely chance for you to use the addition of two integers.
The addition is part of the system you're coding, even if it's embedded via a language API.
But you don't test it. You use it as if it worked the way you intend it to.
Still, some people tested it.
At the hardware level, you might even consider they ran integration tests on it, embedding CPU level cache invalidation and so on.
If you put different names to these layers of testing, you will need to:
- Enumerate different properties for each layer.
- Have different sets of good practises for each layer.
- More importantly, come up with one category per layer you encounter.
But you don't know how many layers of testing you will need to come up with.
You'll discover how many layers you need along the way.
And as we saw before, the different categories of testing you will come up with are not even bierarchical layers, but a graph of stuff more or less related by common properties, tools, or practises.

When you categorize an activity by hardcoding sets of good practises, your categorization becomes hard to adapt.
You want to explain your good practises by keeping them as plastic to the context as possible.
The more situations your are faced with, the more you incorporate to your standards by making them more general.
It's like in TDD with emergent design: the more specific your testing code is, the more general your production code becomes.
Like code refactoring, it's not easy.
It supposes you incorporate the different types of practises into a common vocabulary that makes sense.

The agile manifesto, for example, separates:
- values, that are a given
- principles, directly derivated from values within the context the authors knew at the time.
- practises, derivated from principles
You could go on and on. The thing is, the more you derive rules within a context, the more you become context dependant.
It appears that the practises already have a hard time standing the test of time, and the values can still be considered valid in some organization, and even revolutionary in many others.

For example, roadmapping includes different granularities of things to do.
Jira short sighted users use tasks, then stories, then epics, because they are Jira default categories.
They generally don't differentiate these categories, and blindly use what jira offers them out of the box.
While it's a bad idea to use tools without understanding them in the long term, it's true that you can have a general rule to define a category, from the corporate strategy, or even values, to the task in a todo list.
If we called this generalization a stuff, it could look like:
- A stuff has an end.
- We know how a stuff is progressing by verifying its impact.
- A stuff needs lower level stuff to be done.
- The why of a lower-level stuff is the how of higher-level stuff.
- We must revisit a stuff statement at regular intervals.
Did you see me define the properties of a system that we can test in property-based testing?

Another example is double-loop learning.
When you develop a system, you develop it by discovering the needs of your users. That's the first loop.
Then you improve your process by learning how you work as a team.
Then you improve your process improvement process.
And so on, until 2 consecutive loops become one and the same.
There are common features in these loops. For example:
- You want to keep enough room for learning and adapting.
- The learning process evolves.
- You account for uncertainty in every loop.
- As much as possible, you want to decrease uncertainty with a scientific process.
Then you can derive these rules for the context of each loop.

When you can generalize such a categorization, you can think in a unified way about an activity.
It's easier for you to have a common ground at a high level, while being able to zoom in when required.
It decreases you brains blood weight.
