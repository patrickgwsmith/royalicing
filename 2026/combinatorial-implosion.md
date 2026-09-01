---
date: 2026-09-01T02:10:00Z
---
<meta property="og:published_time" content="2026-09-01T02:10:00Z">

# Combinatorial Implosion

_LLMs contain models for a wide range of observable systems. You can use a coding agent to extract those and encode them as code. The critical next step is to compress to find forms that take up less space, by eliminating moving parts and merging overlapping states into one._

If you imagine your feature as a black box, think of the inputs and what the expected outputs are. What does the user have to do upfront? What are they expecting as a result? What things can go wrong?

If you map this out you can then model the steps that must be done in between. What is expected to be stateful: what does the user expect to still be around when they next use your app, and what do you need to keep track of for auditing purposes? What external systems do you need to talk to in order to get the job done, and will you be modifying any of them?

With this mental model in mind you can imagine the moving parts and the wiring necessary to have something working. You can then interrogate the existing code to see if it matches this model.

Use LLMs what they are great at: language. Write out your mapped black box mental model and point it at the code and ask if they agree.

Look through the code and try to find variables that swim together in schools. When one variable changes value, does another also always change? Perhaps you can merge them into one.

Look especially close at state that is persisted. Actively hunt for pieces that can be derived from other pieces, and uproot those derivatives. Ask what’s the most minimal representation that lets you get to the working state you need in memory. Get your AI from a blank slate to come up with a few options. And then interrogate it about everything that looks superfluous. Simmer it down until you have a thick gravy full of nutrients and no filler.

Find all the failure points. How many escape roads are there out of the happy path? A few? Dozens? Many dozens?

Ask if an outsider needs to differentiate the error on line 21 from the one on line 24. Or are they the same class of error? Think of your black box again and imagine all the kinds of failures you care about. If the internet is disconnected, can this be one failure mode, and become one error in the code? If the disk is full a human probably needs to be told so they can decide what can be deleted.

See if you can pull guards that block bad data up so lower down functions are given well-structured data that they can trust, and avoid defensively checking it again.

Ask your coding agent what the most critical errors are for the type of function you are writing. Soak it in context about your domain so it can suggest informed failure modes. See if it can collapse the many possible ways of things going wrong by writing a shorter list. Then get it to apply that list to your code.

The best way to set up defences is to understand the offensive attack. We can apply the same thinking for security. What are the cracks it can find in your black box model of your problem? Are those cracks sealed up in your current code? If there’s a bad actor trying to get into your system, can you block them early by returning early? If someone’s a bad patron you can boot them out.

Can you remove flexibility that’s been smuggled by scope creep or an eager AI, and reduce the surface for errors or attacks? Remember you can always add it back in later if you need. But it’s a lot harder to remove functionality once it has shipped: Hyrum’s law states that all observable behaviors of your system will be depended on by somebody.

So it’s best to only deliver observable behavior that deliver actual value to users. Otherwise you have accidentally left a clause in your contract that by shipping you become afraid removing will cause users to terminate this contract. Use AI to whittle down this contract to only what you intend to promise.

With these techniques can you avoid the combinatory explosion of state, errors, and bugs that thousands of lines of code can bring. The more code you add to a system the greater the number of combinations. This variety is fun in a game like GTA (unless you do their QA) but less fun in a software product sold to professionals who expect it to work as well as it did last week.

They don’t want one of the unreviewed code combinations to explode: taking the app they rely on down or sending shrapnels of their private data out.

This is why you want to reduce the complexity of code as much as possible. Fortunately AI makes this easier. They are excellent at language, are familiar with a bunch of real-world models, and have enough intelligence to find redundant code and edit it to its essentials.

Just because coding agents let you place a brick on the accelerator doesn’t mean you have to write code like you’re in a Fast and Furious drag race. Identify all the combinations and place the brick intelligently to squish all the air bubbles out. By having fewer lines of simpler code you’ll feel more like reading it too!
