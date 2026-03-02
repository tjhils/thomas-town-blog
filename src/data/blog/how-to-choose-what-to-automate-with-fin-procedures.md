---
title: "How to Choose What to Automate with Fin Procedures"
description: "Not every support ticket should be a Procedure. Here's the framework I use at Wingspan to decide what gets automated—and what doesn't."
date: 2026-03-02
tags: [customer-support, ai, automation, fin, intercom]
---

We rolled out Fin at Wingspan last quarter, and like every team that deploys an AI agent, we started with the wrong question.

"What should we automate first?"

Six weeks later we had twenty Procedures, a 40% automation rate, and a CSAT score that made me want to hide under my desk. We automated the wrong things. Fin was confidently giving wrong answers about refund eligibility and routing complex billing disputes to... itself, in an infinite loop.

Here's the thing about Fin's Procedures: they're powerful. You can teach Fin to pull data from your CRM via API connectors, execute branching logic with if/else conditions, enforce strict business rules with code blocks, and escalate when confidence thresholds aren't met. Fin's customer base reports resolution rates between 30-95% depending on implementation quality. Anthropic saved 1,700 support hours in a single month. But power without judgment just creates faster mistakes.

I scrapped most of our early Procedures and started over with a framework. This is what actually works.

## The Pre-Flight Check: Three Questions Before You Build

Before I open Fin's Procedure builder, I run through three filters:

**1. Is this deterministic?**

Fin excels at clear inputs and clear outputs. If a human reads your documentation and knows exactly what to do every time, Fin can probably do it.

Good candidate: "Check if user's subscription is active. If yes, generate invoice. If no, explain why."

Bad candidate: "Handle upset customers with empathy" (what does that even mean to a machine?)

If your docs contain phrases like "use your judgment" or "it depends," Fin will hallucinate. Don't build a Procedure.

**2. Does it happen weekly?**

That weird edge case that hits twice a year? Your senior agent handles it in 10 minutes. Teaching Fin that workflow takes two days of building, testing, and refining. Do the math.

My rule: needs to happen at least weekly to justify the setup cost.

**3. What's the cost of being wrong?**

Fin suggesting the wrong help article is annoying. Fin processing a $500 refund it shouldn't have? That's a problem I have to explain to finance.

High-stakes, low-frequency = human. Low-stakes, high-frequency = Fin Procedure.

## The Three Buckets: Where Fin Actually Helps

Once something passes the filter, I sort support work into three buckets. Each gets a different Fin strategy.

### Bucket 1: Information Relay (Automate Immediately)

These are tickets where the customer needs a specific piece of information that already exists somewhere—your database, your docs, your policy PDFs.

- "How do I change my payout account?"
- "What's the status of my verification?"
- "Do you support two-factor authentication?"

**The Procedure:** Fin pulls the data via connectors and packages it conversationally. These are your easiest wins—I've seen teams hit 80%+ resolution rates on pure information requests.

**The catch:** Your source data needs to be accurate. I spent a week auditing our help docs before turning Fin loose on these. Every outdated screenshot becomes a wrong answer. Fin can't tell that your UI changed in December if your docs still show the old flow.

### Bucket 2: Simple Workflows (Build with Guardrails)

These involve taking action, but within tight, predictable boundaries.

- Password resets
- Generating invoices
- Updating profile fields
- Scheduling standard callbacks
- Subscription cancellations with prorated refunds

**The Procedure:** Clear steps with verification built in. Fin's branching logic handles the decision tree—if subscription is annual, calculate prorated refund; if monthly, process full cancellation. But Fin confirms before acting, not after. "I can reset that password. Should I proceed?" beats surprise account changes.

I learned this the hard way. One of my early Procedures auto-upgraded users to a paid tier when they hit certain usage limits. Seemed efficient. Then someone's kid clicked around on a shared computer and triggered three upgrades in ten minutes. Now every action Procedure I build has confirmation steps and rate limiting.

**Code enforcement:** For strict rules, I write enforcement logic directly instead of trusting natural language:

```
if refund_amount > 500:
    escalate_to_human()
else:
    process_refund()
```

When the stakes are high, deterministic beats conversational.

### Bucket 3: Judgment Calls (Don't Build Procedures)

These require context, nuance, or reading between the lines. No Procedure here—just escalation.

- "I'm frustrated and thinking about leaving"
- "Your competitor offers this..."
- Complex billing disputes
- Anything involving a child account or vulnerable user

**Why Fin struggles:** The words on the screen aren't the whole story. Tone, history, what's *not* being said—these matter. A human picking up on "I guess I'll just cancel" versus "I'm canceling" can be the difference between saving an account and watching it walk.

**The exception:** Fin can still help by gathering context before escalation. "I see you've contacted us three times about this. Let me connect you with a specialist who can dive deeper." That's a Procedure worth building—Fin acts as an intelligent intake layer, not a replacement.

## The Fin Flywheel: Train, Test, Deploy, Analyze

Most teams rush from Train to Deploy and skip the middle stages. Don't.

**Train:** Write in natural language like you're explaining it to a new teammate. Or let Fin draft from your outline.

**Test:** Fin's Simulations system runs automated tests with AI acting as simulated customers—angry ones, confused ones, edge-case obsessives. I put every Procedure through at least twenty scenarios. If Fin's responses make me wince, I rewrite. If I catch myself thinking "eh, good enough," I delete it. "Good enough" in testing means "embarrassing failure" in production.

**Deploy:** Roll out gradually. I start at 10%, watch metrics for 48 hours, then scale.

**Analyze:** Review override reasons weekly. Patterns emerge fast—missing connectors, unclear branching, edge cases you didn't simulate. Fix and redeploy.

## Measuring What Actually Matters

Don't track "tickets handled by Fin." Track:

- **Resolution rate without human touch** — Did Fin actually solve it, or just deflect? Quality implementations see 50-80% on simple workflows.
- **CSAT on Fin-handled tickets** — Segmented by bucket type. I've seen 30% CSAT lifts when Fin handles the right tickets and hands off the rest gracefully.
- **Human override rate** — If agents constantly fix Fin's work, your Procedure is wrong.
- **Reopen rate** — Did the customer have to ask again? Target under 5%.
- **Time saved** — Anthropic's 1,700 hours in a month isn't typical, but it's directionally correct when you automate the right volume.

At Wingspan, we review override reasons in our weekly sync. The patterns are usually obvious: missing connector data, unclear branching logic, edge cases we didn't simulate. Fix the Procedure, redeploy, measure again.

## The Meta-Point

Fin Procedures aren't about replacing humans. They're about freeing your team to do human things.

Every ticket Fin handles well in Bucket 1 or 2 is energy your agents can spend on Bucket 3—the complex, emotional, high-value work that actually moves retention and loyalty.

The goal isn't 100% automation. It's 100% of the right tickets automated, and 100% of the wrong tickets getting a human who has the bandwidth to care.

Build accordingly.
