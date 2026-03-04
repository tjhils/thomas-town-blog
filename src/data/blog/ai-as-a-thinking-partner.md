---
title: "AI as a Thinking Partner"
date: 2026-03-03
description: "How a Claude plugin called Ideation turned messy voice memos into structured project plans, and why it's useful far beyond software development."
tags:
  - ai
  - claude
  - productivity
  - tools
---

Most conversations about AI focus on what it can generate. Write this email. Summarize that document. Build me a landing page.

That stuff is fine. But the use case I keep coming back to is thinking. Not generating output, but working through problems that are too tangled to hold in your head all at once.

A plugin called [Ideation](https://github.com/nicknisi/claude-plugins/tree/main/plugins/ideation), built by [Nick Nisi](https://github.com/nicknisi) for Claude Code, is the best tool I've found for it.

## What it does

Ideation accepts a "brain dump" and turns it into something you can act on. Project plans, scoped phases, success criteria. Nick built it for software projects, but the underlying mechanic works for any kind of complex work.

You throw messy, unstructured thoughts at it. It evaluates how well it understands your problem and asks targeted questions when it needs more. Once it is confident it has the full picture, it generates a plan and breaks the work into phases with clear specs.

But it goes further than organizing your words. It pressure tests your thinking. The clarifying questions often surface gaps you did not realize were there. (Which, if you have ever walked out of a planning meeting feeling great only to realize the next morning that nobody defined "done," you know is worth a lot.)

## How I actually use it

My workflow starts with [Wispr Flow](https://www.wispr.com/), a voice to text app. I talk through whatever problem I'm stuck on, stream of consciousness style, and let it transcribe. The messier the better.

Then I paste that transcript right into Claude and let Ideation take it from there.

This combination is fast. Talking is faster than typing, and I reason through problems differently when I'm speaking out loud rather than staring at a blank document. Wispr Flow captures the raw thinking. Ideation gives it structure.

## A real example

At Wingspan, we needed to improve our complaint detection process. This touches multiple teams, involves layered regulatory definitions, and is brutal to do well manually. Using AI to help was an obvious direction, but figuring out the specifics was tricky.

I talked through the problem for a few minutes, fed the transcript into Ideation, and answered its clarifying questions. What came out was a plan with clear phases, test steps for validation, and a breakdown of work chunks that made the project manageable.

From there, Claude created a project in Linear, turned the actionable steps into issues, and updated those tasks as I worked through them. The whole chain (voice memo to managed project board) took less time than a single planning meeting would have.

## Second brain thinking

This is what I mean when I say AI is useful for thinking. The Ideation plugin acts like a structured thinking partner. It forces you to be clear about what you are solving, what success looks like, and where the boundaries are. The confidence scoring will not let you skip past ambiguity.

This is still Claude under the hood, with all the usual caveats. It can miss context, ask questions that feel redundant, or produce specs that need editing. But as a first pass at turning chaos into structure, it is better than anything I have tried, including just sitting down and outlining it myself.

## Worth investigating

Nick Nisi has built several other [Claude plugins](https://github.com/nicknisi/claude-plugins) worth looking at. Ideation is part of a broader collection that includes content writing, developer experience tooling, and more.

> **How to install**
>
> 1. Open the **Cowork** tab in the Claude desktop app
> 2. Click **Customize** in the left sidebar
> 3. Click the **+** next to "Personal plugins"
> 4. Select **Browse plugins**
> 5. Switch to the **Personal** tab, click **+** again
> 6. Select **Add marketplace from GitHub**
> 7. Search for `nicknisi/claude-plugins`
>
> You will find Ideation along with the rest of Nick's collection.

If you spend any part of your day untangling complex problems, give this a try. The worst case is you wasted five minutes talking to yourself. The best case is you walk away with a plan you actually trust.
