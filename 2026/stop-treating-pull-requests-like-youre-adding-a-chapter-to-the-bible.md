---
date: 2026-07-29T01:45:00Z
---

# Stop treating pull requests like you’re adding a chapter to the bible

Code review has gotten so blown up in importance the past several years. We forget that code is mutable like wet clay, and isn’t permanent once merged.

It’s been exacerbated because management doesn’t allow paying down tech debt. Rewriting is seen as a sin. So we have this window where many rewrites are actually allowed as long as it’s in a pull request. But once it’s merged it gains a higher status and must see out its tenure like an elite no one likes.

We’ve got to stop micromanaging people and barraging them for making code better because “the ticket is closed”. Coding agents now make refactoring much cheaper. Trust the people who are experts in the medium to control the weeds.

Encourage people to write code to a high standard, educate them on what that means (put days aside for training), give them tools that boost quality, and bias towards merging.

Then review the code that’s in main as a group. Talk about patterns you like and don’t like, and what’s working about the chosen architecture. Don’t spend weeks creating style guides no one reads (not even your LLM), make main great and repeatedly put your focus there. And stop treating pull requests like you’re adding a chapter to the bible.
