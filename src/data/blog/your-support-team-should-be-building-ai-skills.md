---
title: "Your Support Team Should Be Building AI Skills"
date: 2026-03-03
description: "Most AI skills are built by developers. But the people best positioned to teach AI how to do the work are the ones already doing it. Here's how non-technical teams, especially in customer support, can build skills that give them real leverage."
tags:
  - ai
  - customer-support
  - skills
  - cx
---

Most of the conversation around AI skills is aimed at developers. Browse any skills marketplace or tutorial and you'll find instructions for code linting, git workflows, and deployment pipelines. This makes sense. Developers built the tools, so developers built the first skills for them.

But here's the thing: the people who do the most repetitive, pattern-based, documentation-heavy work in most companies aren't engineers. They're support teams. They're the ones answering the same fifteen questions in slightly different configurations, five days a week. They're the ones who already have the playbooks, the macros, the tribal knowledge trapped in someone's head or buried in a shared doc that hasn't been updated since last quarter.

I've spent most of my career in customer support. The best ticket is one that never happens. Every ticket, at some level, is a small failure to have helped someone sooner. Skills are one more tool for closing that gap. They're a way to invest upfront so your AI can handle the pattern work that eats your team's time, freeing them up for the stuff that actually requires a human.

The problem is nobody told non-technical teams they could build skills. The documentation assumes you're a developer. The tutorials use code examples. The marketplaces showcase engineering workflows. If you're a support lead who's never opened a terminal, the whole ecosystem reads like it's not for you. It is.

## What is a skill, really?

Strip away the technical framing and a skill is a set of instructions, context, and examples that teaches your AI how to handle a specific type of work consistently.

Think about what happens when you onboard a new support agent. You don't just say "answer tickets." You give them your tone guide. You walk them through your refund policy. You show them what a good first reply looks like versus a bad one. You tell them which tools to check and in what order. You point out the gotchas: "if the customer mentions X, it's almost always actually Y." (Every support team has about fifty of these. You know exactly which ones I mean.)

A skill is that onboarding, written down in a way your AI can use.

Without a skill, every time you ask your AI to help draft a response or investigate an issue you're starting from zero. You re-explain the context. You correct the tone. You remind it about your refund policy again. With a skill, that context is loaded from the start. The AI already knows your team's voice, your product's quirks, and the common failure modes your customers hit.

The difference between a generic AI assistant and one with your skills installed is the difference between a temp on their first day and a teammate who's been on the team for six months.

## How to spot when you need a skill

Not everything needs to be a skill. If you're asking your AI for a one-off task you'll never repeat, just ask. But there are patterns that signal you're doing work a skill could handle.

**You keep giving the same instructions.** If you find yourself typing "remember, our tone is friendly but not casual" or "always check the customer's plan level before suggesting a fix" into every conversation, that's a skill. Those instructions should be loaded automatically.

**You're copy-pasting context.** Maybe you paste in your refund policy every time a refund question comes up. Maybe you drop in a list of known bugs. If you're regularly providing the same background information to get a useful response, that context belongs in a skill.

**The AI fails in the same way every time.** This is the biggest signal. If your AI keeps suggesting solutions that don't apply to free-tier users, or writes replies that sound nothing like your team, or misses a step in your troubleshooting flow, those are predictable failures. Predictable failures are teachable. That's what skills are for. Thankfully, most AI failures in support are boringly consistent.

**You can describe what good looks like.** This one comes from setting metrics for CX teams, but it applies here too. If you can articulate what a great output looks like, and you can also describe how someone might get it wrong, you can teach it to an AI. Can you explain what a good refund response includes? Can you point out what a bad one misses? That's enough to build a skill.

There's a useful exercise borrowed from the world of CX metrics. When setting a team metric, ask: how would you game this? How could someone move the number without actually improving the experience? That same thinking works for skills. If you can describe both what you want the AI to do and the ways it might technically comply while missing the point, you've got the raw material for good instructions.

## Building your first skill

You don't need to write code. You don't need a computer science background. What you need is the thing you already have: a deep understanding of the work.

### Pick one task

The first skill I built was for creating Fin AI procedures. I didn't start there because it was simple. I started there because it was the task where I was wasting the most time re-explaining context to Claude every time I sat down to work on one. If you're not sure where to start, look for that: the task where you keep doing the same setup work before the AI can be useful.

Good candidates tend to be things like drafting first replies to a common question category, classifying incoming tickets, writing internal summaries, or generating troubleshooting checklists. The key is picking something you do often enough that the upfront investment pays off. A skill that takes you an hour to build can improve every AI-assisted interaction of that type going forward.

### Gather the knowledge

This is the part that feels least like "building" and most like "documenting what you already know." That's because it is. Pull together everything the AI would need to do this task well:

- **Your process.** What steps do you follow? In what order? What do you check first?
- **Your context.** Product details, policies, known issues, plan-level differences. But also organizational context that your team takes for granted: who handles what, what L1 covers versus L2, which engineering teams own which parts of the product, what the escalation path looks like. Your AI doesn't know any of this unless you tell it.
- **Your product vocabulary.** Your customers don't use the same words your product does. A customer says "products" but your platform calls them "listings." A customer asks about their "balance" but that word means two different things in your app. A [great episode of The Support Stack](https://www.customersuccess.cx/support-stack/support-stack-episode-11-teaching-fin-your-product-language) covers how one team built internal glossaries mapping customer language to product terms. They cut their knowledge base from 230 articles to 55 by making each entry work like a prompt the AI could actually use. That foundational terminology work should come before you build anything more complex.
- **Your examples.** What does a good output look like? What does a bad one look like? Real examples from your own work are worth ten abstract descriptions.
- **Your edge cases.** Where does this get tricky? What are the gotchas that trip up new teammates?

I've found that feeding Claude detailed context on our company's team structure, support levels, product ownership, and product vocabulary has been one of the highest leverage things we've done. It's not glamorous work. It's basically writing an internal wiki page. But it means the AI can route, triage, and draft responses that actually reflect how your organization works instead of guessing.

You probably already have most of this scattered across help docs, Slack threads, internal wikis, and your own memory. The work is gathering it into one place.

### Write the instructions

Write your skill the way you'd brief a capable new agent on their first day handling this type of task.

Be direct and specific. "Write in a friendly tone" is vague. "Open with the customer's name, acknowledge their issue in one sentence, and keep the total response under 150 words" is something the AI can work with.

Use conditional language. "If the customer is on a free plan, do not suggest features that require a paid plan" is useful. "Be mindful of plan levels" is not.

Include the "why" when it matters. "Always ask for the order number before looking up a refund, because customers often have multiple orders and the most recent one isn't always the one with the issue" is better than "always ask for the order number."

Include the human stakes too. Your AI should understand that a customer who can't launch their page on time might be facing real financial consequences. That context changes how urgently and carefully the AI should handle the interaction. Without it, you'll get technically correct replies that completely miss the moment.

A practical template:

- **Purpose:** What is this skill for? (For the Fin procedure skill: "Build or improve Fin AI procedures using our accumulated best practices, data connector context, and known resolution gaps.")
- **When to use it:** What triggers this skill? What types of tasks or questions does it apply to?
- **Context:** Background information the AI needs. Policies, product details, known issues.
- **Steps:** The process to follow, in order.
- **Examples:** At least one good output and one bad output. Real ones from your team's actual work.
- **Constraints:** What should the AI avoid doing? (For the QA plugin: "Never modify a score after it's been approved. Support Managers cannot edit the calibration framework directly.")

### Test and adjust

Run your skill against real scenarios. Use conversations your team has already handled. Compare what the AI produces with your skill to what your best agents actually wrote.

It won't be perfect the first time. Look for patterns in where it falls short. Is it missing context you forgot to include? Is it following your instructions too literally? Is the tone off? Adjust and test again.

Take this seriously. A bad skill is worse than no skill. It will confidently apply outdated or wrong information to your customer interactions. Your support team is often the primary point of interaction a customer has with your brand. A skill that gives wrong answers at that touchpoint doesn't just waste time, it actively damages the relationship.

If your AI tool supports it (and many do, including Claude), you can run simulations or test conversations that let you validate the skill's behavior before it touches a real customer interaction. Use that. It's free practice.

## What this looks like in practice

The process above might sound abstract, so here's what it actually produced for our team.

The first skill I built packaged everything we knew about creating Fin AI procedures. Fin is Intercom's AI agent, and procedures are the multi-step workflows you build to handle specific types of customer questions. Our team had accumulated best practices from documentation, podcast episodes, community implementations, and our own trial and error. We had context on our existing data connectors and a clear picture of which common questions Fin was struggling to resolve on its own.

None of that knowledge was in one place. It lived across a dozen sources and in the heads of a few people on the team. The skill became the container that brought it all together. Now, instead of reconstructing that context every time we need to build or improve a procedure, it's loaded and ready.

I won't pretend the first version was great. It took a few rounds of testing against real conversations to get the instructions dialed in. But the important part was that once it worked, it worked for everyone on the team, not just the person who happened to know all the context.

Skills can get more ambitious than that.

Our team also built a QA scoring plugin that connects Claude to Intercom, Linear, and our production database. The problem it solved was straightforward: QA was eating about six hours a week and still wasn't giving our agents the feedback they deserved or our customers the consistency they should be able to expect. Not because we didn't care, but because the mechanical work of pulling a ticket, reading the conversation, checking whether the agent's claims were accurate, applying the rubric, and writing coaching notes took 20-30 minutes per ticket.

The plugin handles the mechanical parts. It fetches the ticket, identifies the agent, loads our scoring rubric and calibration notes, checks agent claims against the production database (did the customer actually have the plan the agent said they did?), and scores against five attributes. The human reviewer looks at what the AI produced and focuses on the judgment calls: does this coaching note capture what went wrong? Is the process the agent followed the right one, or is our documentation the problem? Should we update the rubric based on what we're seeing?

It also tracks calibration. When two reviewers score the same ticket differently, the plugin surfaces the gap so we can align on what a "3 for Knowledge and Accuracy" actually means in practice. That kind of consistency used to require scheduling a meeting. Now it's built into the workflow.

Both were built by support people. The difference between them is scope, not technical difficulty. The Fin skill packages knowledge so AI can apply it. The QA plugin packages a whole workflow so AI can run it alongside you.

That Fin procedure skill eventually grew into something bigger. I paired it with a second skill, a content advisor, and packaged both as an [open source Fin optimization plugin](https://github.com/tjhils/cx-plugins). The procedure advisor helps you figure out which procedures to build and in what order. The content advisor helps you diagnose why Fin gave a wrong answer and choose the right fix: a guidance rule, a snippet, a help article, or a procedure. One is proactive (what should we build next?), one is reactive (what went wrong and how do we fix it?), and when a content issue warrants a procedural solution, the content advisor hands off to the procedure advisor.

I published it because the whole point of this article is that support people should be building this stuff, and it's harder to make that case without showing what it actually looks like. If you're working with Intercom and Fin, you can use it directly. If you're not, the structure is worth looking at as a template for how to organize skills that work together.

## Sharing skills with your team

A skill that lives on one person's machine is useful. A skill that lives in a shared library your whole team can use is where the math gets interesting. One person spending a few hours building and documenting a skill can save every agent on the team time on every relevant interaction going forward.

When you share a skill, your teammates need to understand it too. The QA plugin, for example, has defined roles and permissions: the Head of Support can edit the scoring rubric, Support Managers can score their own team's tickets but can't modify the calibration framework. That kind of clarity about who can do what makes a skill usable by someone other than the person who built it. Even for simpler skills, write a brief description of what it does, when to use it, and what it doesn't do.

Treat your skills the way you'd treat your knowledge base articles. Review them periodically. Update them when the product ships something new. Retire them when the process they support no longer exists. Your product shipped a new billing flow last month but your skill still references the old one? Congratulations, your AI is now confidently giving wrong answers at scale. (Ask me how I know.)

## What changes when support teams build skills

There's a larger thing happening here that goes beyond efficiency.

Support teams have always struggled to be seen as strategic. The work is constant, the value is hard to quantify, and the institutional knowledge lives in people's heads where nobody outside the team can see it. Skills change that equation. When your team's expertise is encoded in a skill, it becomes visible, shareable, and something you can point to and say: this is what our team knows, and here is the measurable impact of that knowledge.

A skill library is a support team making its own case. Not with a deck about cost avoidance or a report on churn correlation, but with working tools that demonstrate what the team's expertise actually produces when it's applied consistently.

If you're a support lead reading this and thinking you don't have the technical chops to build skills, I'd push back on that. You already have the hardest part: years of pattern recognition, a deep understanding of your customers, and opinions about what good looks like. The tooling is catching up to you. Take an afternoon, pick one task your team does every day, and write down what your AI would need to know to do it well. If you want to see what a finished plugin looks like, the [Fin optimization plugin](https://github.com/tjhils/cx-plugins) is open source and MIT licensed.

The best ticket is one that never happens. The best skill is one that carries your team's thinking forward, consistently, whether the person who wrote it is online or not.
