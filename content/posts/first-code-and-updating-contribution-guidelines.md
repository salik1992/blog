---
title: 'First Code and Updating Contribution Guidelines'
date: '2026-09-07T22:43:43+02:00'
tags: [TSP, developing with Grok]
categories: []
---

Well enough of experimenting, planning and stalling. Today was a day to actually ask for a first proper code.
I started with the easiest of the components of the repository and it worked quite well. I had only a few comments
to make to match the code style to something that I would actually write.

One of the things I wanted to change was also an import order. But instead of explaining that and potentially
having to spend some context memory on those rules there are already tools that are better for that than LLMs.
For those still wondering, `prettier-plugin-organize-imports` is the answer here. So after merging first real
code PR. It was just a minute or two to let Grok add the plugin, format the code and approve that PR.

## Raising the bar

Well, the easy part was done and to be fair even though the code matched my expectations I'd be disappointed
if it didn't. It was a clear spec and basically nothing to get wrong. Even if given to a less experienced
dev.

Next up was a testing/debugging app. The architecture mentioned its purpose and we have the main component's
interface defined. But there were no other pointers given in the codebase. My prompt was:

> Create the test app using React and Redux. Use Tokyo Night color palette and make it TUI like in look and feel.
> At the top there should be a container element for the videos, below that controls - use plain text for buttons
> and state of the playback. It's a debugging app so raw data are preferrable, just nicely presented.
> At the bottom there should be a form for the initial configuration.

This took some time before Grok produced the code. The resulting PR was longer than what I prefer to review usually.
But about a third of it were styles for that TUI effect that I wanted so it was my issue to deal with this long PR.

Not so surprisingly there were quite a few changes that I wanted to change including a complete refactor of certain part.
In total, I asked for 12-15 changes. Sorry, I forgot to note down the exact number.
This time however I didn't want Grok to just blindly follow my comments so instead of stating "PR review done" I prompted:

> I finished my review. Read my comments, ask about those that are not clear to you and challenge me on those that you
> don't agree with. Don't start with implementing changes yet.

The response was genuinely nice to hear. Seven to ten of those comments Grok marked as "Yeah, makes sense." But there were
five that I was challenged on. For each Grok provided a sound reason on why it thinks my request is not good and also provided
a few alternatives that we could do. Once I gave Grok my decisions on those the second round of PR was prepared.

This is actually why I prefer to use Grok over other LLMs. First, it's not glazing me for each prompt and it is not afraid
to challenge my decisions and tell me why it thinks they suck.

I reviewed the new commit changes, verifying that it matches my requested changes and then I went to test the application.
It looked correct, for functional part that will call the library we kept TODO stubs. So it was mostly about checking the UI.
I noticed a graphical issue with some panel title getting clipped. And I could't help but investigate. I probably could
have asked Grok to try investigate and make changes but my goal is not to fully vibe code something that will somehow work.
My goal is to create an app that will match my coding standards and the resulting code will be indistinguishable from my own
writing. So if the bubble pops eventually and we loose all these tools, the code I'm left with is still understandable and
maintainable. I found the issue within five minutes and asked Grok about it directly. And a small commit later the PR was ready
for merge.

## Changing Contribution Guidelines

As the last change of the day I asked Grok to add a few changes to the Contribution Guidelines to improve our PR review process.
The newly added points were:

- Add a timestamp to the patch file name. This way I can compare what changed easily and I keep the reference to my original comments.
- Apart from inline comments I may add a general feedback at the top of the patch file.
- Once I finish the PR, read the comments, ask about unclear ones, challenge me on those you don't agree with and do not start implementing
  changes until we agres in our discussion.

I really enjoyed that challenge part in the last PR so I want to keep it. It feels a lot more like an actual PR discussion between author
and reviewer, many good ideas came from those so why would I want to avoid them.
