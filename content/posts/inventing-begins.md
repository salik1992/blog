---
title: 'Inventing Begins'
date: '2026-09-08T21:57:36+02:00'
tags: [TSP, developing with grok]
categories: []
---

Funny, today we had a discussion at work about how agents need to be kept on short leash or they will start inventing
more than what is being asked. In the morning I tasked Grok with `Prepare the MediaPool module` but I didn't have time
to review its work until evening.

MediaPool is a module that we have defined in the architecture including what it should do. But we have never discussed
the internal structures. Well, they were crystal clear to me and probably every developer who has done some media players
before but not to Grok.

It pulled features and responsibilities of other modules and put them into this simple MediaPool. But the fix was simple.
I just emphasized that MediaPool should only create / own / destroy media elements and that timing info belongs to Timeline.
It figured out that I meant that those things should be removed, double checked with me on that and then updated the PR.

## One more thing

Yesterday, I spoke about our rule for patch files. Today Grok pulled another trick and created stacked patch with all commits'
changes instead of current state vs master. So we had to update this rule and specify it. :facepalm:

Did the pink new toy glasses break already on day 3?
