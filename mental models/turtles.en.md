#Turtles rule, all the way

Mental models help you take decisions when they fit the reality you're facing.
Many models are too simple to match enough situations.

Many models describe nested systems.
In some of them, the nested systems each have a name, and are described independently.
You want to explain the characteristics of systems by keeping them as adaptable to the context as possible.
When you name each layer, your categorization becomes hard to adapt.
The more situations you face, the more you incorporate them to your model by making characteristics more generic.
It's like in TDD with emergent design: [the more specific your testing code is, the more generic your production code becomes](https://sites.google.com/site/unclebobconsultingllc/home/articles/as-the-tests-get-more-specific-the-code-gets-more-generic).
Cyrille Martraire talks about [raising the water line](https://youtu.be/svh_NxbOJV8), from theory to conciseness, and links this to laziness (which is good for an engineer).
Like code refactoring, it's not easy.
It supposes you incorporate the different characteristics of layers into a common vocabulary that makes sense.

The agile manifesto, for example, separates:
- values, that are a given
- principles, directly derivated from values within the context the authors knew at the time.
- practises, derivated from principles
You could go on and on. The thing is, the more you derive rules within a context, the more you become context dependant.
It appears that the practises already have a hard time standing the test of time, while agile values can still be considered valid in some organization, and even revolutionary in many others.
You can consider agile values as an abstraction of agile principles. Principles are an instantiation of the values in a given context. You can use the values to reason about the situation in a wider range of contexts. And you need the principles to guide you in your concrete context.

Let's dive into some examples.

##Backlog items

Roadmapping includes different granularities of things to do.
Jira short-sighted users use tasks, then stories, then epics, because these are Jira default categories.
Jira users often don't differentiate these categories, blindly use what jira proposes out of the box, and retrofit them in their existing process.
While it's a bad idea to use tools without understanding them, it's true that you can have a general rule to define a category, from the corporate strategy, or even values, to the task in a todo list.
![John Cutler about the coherence needed from tasks to long-term goals](https://twitter.com/johncutlefish/status/1158817067056812033/photo/1)
If we called this generalization a goal ([or an opportunity, or a bet](https://www.infoq.com/presentations/bets-boards-missions-agile/)), it could look like:
- A goal has an end.
- We know how a goal is progressing by verifying its impact.
- A goal may be made up of nested goals.
- The why of a nested goal is the how of its encapsulating goal.
- We must revisit a goal statement at regular intervals.
Did you see me define the properties of a system that we can test with property-based testing?

##Double-loop learning

When you develop a system, you do it by uncovering the needs of your users. That's the first loop.
Then you improve your process by learning how you work as a team.
Then you improve your process improvement process.
And so on, until 2 consecutive loops become one and the same.
There are common features in these loops. For example:
- You want to keep enough room for learning and adapting.
- The learning process evolves.
- You account for uncertainty in every loop.
- As much as possible, you want to decrease uncertainty with a scientific process.
Then you can derive these rules for the context of each loop.

##The test pyramid

The [test pyramid](https://www.mountaingoatsoftware.com/blog/the-forgotten-layer-of-the-test-automation-pyramid) originally assumes that you have 3 layers (unit, service, UI).
Some adapt their test pyramid to their vocabulary, adding or renaming layers.
Anyway, as soon as your system becomes just a little bit complex, the reality becomes more nuanced than that.
You end up with separate modules (microservices? Kidding), each having several layers.

You want to find the right tradeoff, for each test, between:
- Realism: If the test passes, the corresponding use case will work end-to-end in production.
- Speed: you want to run billions of tests in nanoseconds.
- Coverage: you want to test every edge case, imaginable or not.
- Reliability: you want your test to fail because of the feature you intend you test. Generally, [a test is solid when it embeds little stuff](https://testing.googleblog.com/2017/04/where-do-our-flaky-tests-come-from.html).
- Explainability: you know why a test failed.
- And many more properties like these.

For a given category of tests of a given module, you will find the right tradeoff of good practises.
This tradeoff allows you to run tests within a range of values for each of the aforementioned properties.
In the multidimensional space of tests properties, you get a bubble, corresponding to a set of practises.
If you generalize this, you will get one bubble for each test category of each module.

For example, for some tests, you may mock/stub/fake this or that library. For other tests, you may prefer using their real implementations.
For this feature, you want to smoke test the end-to-end plumbing, while randomly generating edge cases at 5000 tests per second, by testing one independent sub-sub domain library.
It depends.

In a simple system, you might be able to call bubbles of practises unit, integration, system, service, UI, or end-to-end tests, in a way that makes sense to you across all your modules.
In more complex systems (for example a polyglot one), what you call a unit test is totally different from one module to the other.

In addition, like all systems, architecture is nested.
The integration testing of a system is the unit testing of a higher level one.

For example, when you code, there is a likely chance you will use the addition of two integers.
The addition is part of the system you're coding, even if it's embedded via the language.
But you don't unit test it. You use it as if it worked the way you expect.
Still, some people tested it.
At the hardware level, you might even consider they ran integration tests on it, embedding CPU level cache invalidation and so on.
And you probably test it indirectly, either by integration tests, or what you naively call unit tests.

If you label layers of testing differently, you will need to:
- Enumerate different properties for each layer.
- Have different sets of practises and tools for each layer.
- Come up with one category per layer you encounter.
But you don't know how many layers of testing you will need to come up with.
You'll discover that along the way.
And anyway, the different categories of testing you will come up with are not even hierarchical layers, but a graph of bubbles more or less related by common properties, tools, or practises.

I prefer sticking to the fuzzy notion of bubbles of properties, tools, and practises.
I adapt this concept to each context, by searching, naming, and describing bubbles.
It prevents me from bending reality to fit the pyramid, thus reducing my brains blood weight.
Oh, and having a set of bubbles already defined for a given product doesn't restrict you from coming up with new ones when it can help.

##Conclusion

Thinking about nested systems as independent layers can help you discover a new topic by giving you concrete cases.
However, you may quickly realize that these hardcoded layers need to evolve to match you context.  
When you can generalize a categorization, you can reason in a unified way about an activity.
You don't want to merge all nested systems in a single description.
That would be fractal, and it would be a very simplistic view of the universe.
You want to make your life easier, having a common ground at a high level, while being able to zoom in when required.
Abstracting a set of categories decreases you brains blood weight.
