---
title: 'Building an Open Source Library With an Agent'
date: '2026-09-06T15:31:08+02:00'
tags: [TSP]
categories: []
---

For quite a few years now I've been carrying a concept of a library for synchronized playback in my head.
But unfortunately I never had time to sit down and start creating. There's always been something of higher
priority, not enough energy or just real-life happenings.

But people seem to use agents to vibe code their apps and put them into various stores. I don't know how
much code those apps contain generated vs. hand-written. What's the quality of that code, how is it with
maintainability... Even linux core now accepts some amount of generated code.

So I got an idea, why not to try to create that library that I wanted for so long and learn to work with
agentic workflows and LLM generated code at the same time? And document it as well :-)

## The Beginning

On purpose, I didn't start with looking into how you manage your work with agent and how others approach it.
I decided to go for it blind. I had a very little experience from the same day using agent for a task
(see my post about my linux journey) and I used web chat interface for various LLMs before.

I created a folder, an empty repository, added my prettier config and started writing a markdown file
of what I want to build, how it should work and I ended up with about 50 lines of unstructrured points.

Then I spawned my Grok (version 4.6) and asked it to read through it. And ask me questions about things
it didn't understand or where it saw some gaps. Ten minutes later I received 32 questions that all made sense.
So I put those questions into a new document (QaA) and started writing responses to all of them. I got
quite surprised how deep some of those questions were. I took some time answering those but mostly I knew
how to deal with various of those situations that Grok presented.

With all the questions answered I prompted it to read both documents again and re-iterate and present
another set of questions where decisions weren't clear or we have gaps in the spec. Ten minutes later
25 even deeper technical questions were waiting for me. I've read through them but since I was already
two hours into the progress, I decided to take a break before answering them to avoid focus tunnel and
also to think how I want to cooperate with Grok on contributions to the repository. Walk in the nature
is perfect for things like these.

## Old Fashioned Approach

Full of energy and new ideas I sat down, wrote responses to those 25 questions from earlier and also
added AGENTS file and CONTRIBUTING guidelines for Grok. The main rules are:
- never commit to master
- never push to remote
- never publish anything to npm

For work I have setup and explained it an old fashioned approach. It makes changes in a branch with
conventional naming based on the task I give it. Once it's done it creates a "pull request" by presenting
me with a patch file. I then review the changes and leave inline comments in that patch file, plus
general feedback at the top and return the steering wheel back to Grok. It is then supposed to implement
my requested changes and once ready present me with a new patch file. Oh how I wish I could write
inline comments like this using GitHub CLI. I still need to rethink this approach so I could keep history
of previous comments because I loose them for now. Fortunately, the most amount changes I have requested
were three so I just checked the last commit Grok created with my requested changes.

Once, I finished setting these new rules up and I tasked Grok to read them and start following them.
It's first task was to compile the initial ideas document and two QaA files into a structured architecture
file. Which grew to whopping 450 lines from the initial 50. There was also a part of the architecture
that Grok wanted to do but I didn't like his proposal and we decided to keep it for later.

## Day 2

I didn't get much sleep, mostly because my brain just kept thinking about that feature we didn't specify.
Anyone's elses brain also refuses to shut down in the night and even though I was pretty tired, it kept me
awake. Later in the day I wrote about 30 points for that feature and how it should interact with rest of
the system. It also required some changes to the interface and followed with two rounds of ask me and I shall
clarify. After that, Grod was tasked incorporate this new behavior into the architecture. Followed by a PR
that set up the skeleton for packages that we agreed upon.

As it sits now, there's a 550 line of architecture documentation and the most basic skeleton of a monorepo.
I still have to see a proper code that it will generate but for now I'm pleasantly surprised. My plan is
that all the generated code will have to meet my criteria for high standards. I won't be satisfied with a huge
code that somehow works and no-one understands it properly. Let's see what the next days of actual coding
will bring.
