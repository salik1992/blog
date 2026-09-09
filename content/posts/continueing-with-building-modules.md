---
title: 'Continueing With Building Modules'
date: '2026-09-09T23:41:11+02:00'
tags: [TSP, Developing with Grok]
categories: []
---

Day 4 was a slower one. I didn't have much time to do code reviews so I reduced the new code to HLS.js wrapper and Synchronizer module.
Both of these parts were pretty straightforward in terms of interface as that is well documented in the architecture.

## Hls.js wrapper

Grok did this flawlessly. It had the HTML5 wrapper already as a reference so it just re-did some parts and added parsing of program date time.
I don't really have much more to say about it.

## Synchronizer

This module is responsible for measuring time diff of every playing unit and tries to align it to the correct time from Timeline.
The rules for synchronization are documented so implementing the decision branching was done correctly. What these changes lacked
are things that you don't really expect if you haven't done something like this before. Like if you seek to synchronize, you can't
just seek to the current point. You need to track the average/last seek time and add that to the seek target. Because while you
seek the Timeline drifts away under your feet so you want to land at correct time in future. Not correct time in the past.

I've listed these things and we added them as TODO comments. It's one thing knowing what to do but other thing doing it while we
don't have other parts of the system to put it together, yet.

I have several busy days ahead of me so it might hinder the progress slightly.
