---
title: "A Second Brain for Managing People"
date: 2026-04-22
description: "How I'm using Claude and Obsidian to log feedback across my team, so reviews are built on real moments instead of memory archaeology."
tags:
  - management
  - ai
  - claude
  - obsidian
  - productivity
---

It's review season, and for the first time in my career I'm not scrambling.

Usually this is the week I disappear into Slack's search bar trying to reconstruct what my team accomplished six months ago. This year I opened Obsidian, opened Claude, and started writing. The queue data (CSAT, resolution time, QA scores) used to do the heavy lifting when my memory came up short. This time it didn't have to.

## What kept breaking

For support managers especially, the failure mode here is well-documented. Three things compound.

First, reviews skew toward what's measurable. QA scores and ticket volume are always there. They crowd out the softer work: the mentorship, the cross-team unblock, the customer interaction that didn't show up on a dashboard but mattered a lot.

Second, memory is a week-of scramble. By the time I'm writing a packet, February is a blur. I end up rummaging through Slack history, DMs, and half-remembered 1:1s, hoping to reconstruct a quarter from scratch.

Third, good work disappears between cycles. If it didn't get logged somewhere durable, it's gone. That stuff mattered in March. By August it's a vibe, not an example.

Honestly, all three were happening to me at once. You can cover for it, in the sense that a manager who's paying attention can usually recall *something*. But the written review ends up leaning heavily on what's easy to quantify, and the person reading it the night before their 1:1 with me can feel the gap.

(Quick caveat. "Leans heavily on what's easy to quantify" isn't a dig on queue data. The data matters. It just isn't the whole picture, and when it's the only thing I can cite by name, the review starts to feel like a performance dashboard with a paragraph wrapper.)

## The vault

Here's what I built. Nothing fancy. The whole thing took a Sunday afternoon.

An Obsidian vault with one page per teammate. On each page: a running feedback log, plus every prior review packet I could find (self-assessment, my manager review, peer reviews). Claude knows the vault's structure and purpose. When I point it at someone's page, it's not starting from zero. It's reading their history.

The key move is what I do in between reviews, not during them. When someone on my team does something worth noting, I hand it to Claude. Sometimes that's a Slack link with two lines of context. Sometimes it's a Linear issue they closed. Sometimes it's a Notion page they drafted that I'd otherwise forget existed. Claude writes it into the right person's log with a date and a tag, and I move on.

That capture step takes maybe thirty seconds. That's the part that makes the whole system work, because a 30-second log actually happens and a five-minute log doesn't. (I know. I tried the five-minute version first and stopped doing it within a week.)

By review time, each teammate's page has a month-by-month record of real moments, not my best reconstruction of them. Claude can read across the log and surface patterns I wouldn't catch by eyeballing it. Growth areas. Recurring strengths. A stall that happened back in February that I'd already forgotten about.

## The bug story

One example from this cycle. A direct of mine caught an open bug in our product. Real one, not something trivial. What made it notable wasn't the catch itself; it was the follow-through. They investigated carefully, proactively shared the known issue in the right Slack channels (including the customer-facing one we usually forget), and communicated clean updates as engineering worked toward resolution. All three pieces together: technical instinct, good judgment about where to raise it, and steady communication over time.

If I'd tried to recall that moment cold six months from now, I'd have remembered the catch. Maybe the fix. I don't think I'd have reconstructed the communication arc, which was honestly the best part. I logged it in thirty seconds when it happened. It showed up in the review as a grounded, specific example instead of a vague "handles production issues well."

## Where the QA tool fits

The other half of this is quantitative. I built my own QA tool with Claude (I walked through the details in [this YouTube interview](https://www.youtube.com/watch?v=OnjU-M_JUUA) if you want the longer version). It chews through my team's ticket samples and produces progress summaries, trend logs, and changes over time per person.

That's the dashboard side. The vault is the story side. On their own, each one feels a bit thin. A trend line without moments is impersonal. A bag of moments without trends is anecdotal. Together they give me something I've never had before: a review packet that makes a real argument about someone's quarter, with evidence on both sides of the data-narrative line.

(Small side note. I spent more time than I'd admit trying to shoehorn my old QA vendor into this workflow before I gave up and built the thing myself. Rest in peace to that stack. The interview covers why.)

## What this actually changed

What's actually changed for me is confidence.

I've always felt some amount of dread around review season, the quiet worry that I was going to miss something important about someone. Not because I don't pay attention, but because the cognitive load of tracking growth across a whole team, across a whole review period, without a system is genuinely hard. You can't hold it all.

This year that feeling is gone. When I write a section about someone, I'm drawing from an actual record. I can tell you what they did in March, not just what they did last week. The review has more concrete examples beyond queue data, and the feedback I'm giving in 1:1s is more specific too, because I'm not only thinking about the last sprint.

Here's the broader point. Engineers have been building second brains for years. Obsidian, Roam, DEVONthink, the whole genre. The argument has always been that knowledge work benefits from externalizing memory. Managing people is knowledge work. It's pattern recognition across humans, over long time horizons, under high stakes. Why wouldn't the same tools apply?

They do. I just hadn't seen many managers building for it. Most of the manager tooling I've encountered is performance-review software that wants you to fill in boxes three weeks before the deadline. That's not a second brain. That's a form.

## Start smaller than you think

If this is resonating and you're a manager who doesn't have something like it, the advice I'd give is to skip the system design phase, make a doc per teammate, and log one moment today. See if you use it next week.

Everything I built on top of that (the Claude integration, the QA tool, the structured vault) came from a year of noticing which habits stuck and which didn't. The doc-per-person is the part that earned its place first. The rest is scaffolding around that one habit.

You don't need my exact stack to start. Obsidian and Claude are what I reach for, but any second brain tool paired with an AI assistant will get you most of the way. The habit is the thing. The tools are how you keep doing it when you get busy. You just have to decide that your team's growth is worth writing down.
