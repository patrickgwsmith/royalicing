---
date: 2026-08-18T00:56:00Z
---
<meta property="og:published_time" content="2026-08-18T00:56:00Z">

# Faster pull requests are faster horses

_Perhaps we should throw out the rubber stamp and just commit to main? How would we then work?_

The pull request was an intentionally thoughtful checkpoint to ensure the paperwork of programming was in order. But now with AI the paperwork has been delegated to coding agents. Big teams have a massive bottleneck because so much is being merged in, the branch is out of date in minutes and has to be rebased yet again. And it seems barely anyone reads or writes the commit messages.

The coordination of an ordered commit log is fruitless if your parallel development process is intentionally uncoordinated. The only logs your customers care about are the changelog and the incident log.

Richard Hipp talks about verifying both source code and verifying compiled code in SQLite. A green test suite is not enough. You test the logic of the code that you author and you test the behavior of the program that you ship. Fuzzing lets virtual cops interrogate the suspect until they squeal “I did it, I was off-by-one, it won’t happen again, I swear!”

Their “don’t trust, verify” philosophy even extends to compilers. [Richard says](https://youtube.com/watch?v=V_qzqY1bb7I&t=1027) “SQLite in its history has found bugs in each of GCC, clang, and MSVC.”

We could also mix in ideas of how Google/Amazon/Meta continuously release software.

We could expose the built program to shadow traffic mirrored from production requests. It starts life in a simulation.

We could expose the built program to a tiny sliver of real world traffic as a canary, and leave it to bake for hours while we measure error rate, latency, memory & CPU usage. Eventually if the temperature looks right it’s served to all users.

At each step we verify from a different angle. We iteratively go from synthetic inputs and limited consequences to real users and real consequences. We put each version of the program through the Twelve Labours of Hercules, where our hero only progresses after surviving each challenge.

Does this empirical approach mean we don’t need to review the code? Not at all.

We worry about pull request code review today because that’s what we decided to worry about before AI agents. We decided to act as bouncers for each other, stopping “bad” code from entering at the door, rather than having conversations about what desirable code is and trusting each other to deliver that.

I believe we should be reviewing code more broadly. Checkout main and wander through the neighbourhood you are spending time in. Pay a call to your neighbours by reading the comments they left and even talking to them.

It’s called “code” because it encodes an understanding of a solution to a problem. If you are debugging a production issue then it’s critical that you can decode the logic and understand the moving parts at work. Re-reading code files is a great way to do this. Reading code only as diffs is like trying to view an elephant through a straw.

The code is a communication medium and a pull request’s code diff is often a soundbite without context. Viewing just the pieces of code that changed feels efficient but your judgement is limited unless you are deeply familiar with the current state of the surrounding code. You can better appraise alterations if you have the map in your head. And much better if you drew the map.

Trying to assess code changes by detached diffs is like trying to assess the value of a publicly-traded company by its latest share price movement. Unless you understand a company via its history, competitors, and related industry news, it’s very difficult to wisely trade its stock.

NVDA +2.7% looks a lot to me like +27 lines, −19 lines. Do you buy, sell, or hold? Do you merge, reject, or huddle?

Code is a strange shape-shifting substance because to a business it’s both an asset and a liability. If code is understood by no one in the org then its liabilities risk compounding faster than its value. If you are tethered to coding agents for making any progress then all your understanding is leased.

Henry Ford supposedly said: “If I had asked people what they wanted, they would have said faster horses.” Faster pull requests sounds to me like a faster horse. We need to find the automobiles for the agentic coding age, and master their manufacturing.
