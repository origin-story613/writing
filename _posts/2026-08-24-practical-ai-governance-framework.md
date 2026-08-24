---
layout: post
title: "A practical AI governance framework (and what agent files change about it)"
date: 2026-08-24
categories: [ai-governance]
excerpt: "Combining and expanding four earlier posts into one working framework — registry, risk tiers, review process — plus what AGENTS.md-style files mean for the whole thing."
---

I wrote about a marketing coordinator a few weeks back. She found an AI writing tool on a Tuesday.

By the end of the week, she'd pasted member survey data into it to draft a newsletter. Names, email addresses, a few open-ended comments about member complaints.

Asking first never occurred to her. There was no policy to point to and no one to check with. She isn't careless, and there's no malicious actor in this story.

Her manager finds out three weeks later, during an unrelated audit. The coordinator was just trying to get a newsletter out by deadline.

That's what AI governance failure actually looks like. A normal person doing normal work, inside a policy vacuum.

I've spent the last several months building a framework at the Y to close that vacuum, and I wrote about the pieces separately as I built them: a registry, risk tiers, a review process. I'm putting them in one place, with more of the practical detail I left out the first time, plus a new fourth part that changes how I think about all three.

## The registry

Most organizations find out what their AI policy is after something goes wrong. They write the rule in reaction, then post it in a shared drive next to the brand guidelines nobody reads.

Skip that. Start with a spreadsheet, five columns:

**Tool name.** Whatever staff are actually using. ChatGPT, Canva's AI features, the browser extension someone installed without asking.

**Department.** Who's using it. If it touches your branch or the org chart, it goes on the list.

**Data touched.** The column that matters most. Member names? Financial info? Nothing at all, just brainstorming copy? Be specific. "Some data" isn't an acceptable answer, and I'd push back on it every time I saw it in early drafts of our own list.

**Who approved it.** Even if the answer is "no one yet," write that down. It tells you where the gaps sit.

**Review date.** Pick a frequency and stick to it. Tools change, approvals expire, and a registry that's a year stale is worse than no registry, because it gives you false confidence.

That's the whole thing. Five columns, a shared spreadsheet, one afternoon to build.

What I didn't say clearly enough the first time: a registry only tracks what gets entered. It won't catch a tool someone starts using, never reports, and is never asked about. That needs a separate check, a manager asking directly twice a year, or a periodic look at what's actually installed on work devices. Something that doesn't depend on people volunteering information they don't know they should volunteer.

## The risk tiers

Not every use case carries the same weight, and treating them all the same either slows everything down or lets everything through. Three tiers:

**Tier 1, low risk.** Internal drafting only, first drafts and brainstorming, not the final product, with no member data or financial systems involved. A staff member roughing out a newsletter in ChatGPT qualifies here, since a person still reviews and finalizes it before it goes anywhere. Approval: a quick manager sign-off, logged in the registry, done same day.

**Tier 2, medium risk.** Member-facing content with no personal data involved. Social posts, email copy, website text. The output reaches the public, but no names or member records touch the tool. A branch coordinator drafting an Instagram caption sits here. Approval: a short review from marketing leadership before it goes live.

**Tier 3, high risk.** Anything touching member data, financial systems, or HR records. The coordinator's newsletter from the opening story belongs here, member names and complaint details pasted into a tool with no oversight. Approval: sign-off from IT and legal, not just a manager. This tier moves slower on purpose. That's what makes it work.

Most requests land in tier 1. A working tier system speeds up the easy calls as much as it slows down the hard ones, because nobody has to escalate a newsletter draft to legal just to be safe.

## The review process

Marketing brings the use case. IT checks the data path. Legal checks the exposure. That's the meeting, when a meeting is even needed.

Marketing's job is naming the actual task, not repeating the tool's marketing copy back. "We want to draft newsletter content faster" is a use case. "We want to use AI" is not, and I've learned to send that second kind of request back for a rewrite before it reaches anyone else.

IT's job is the data path: where does information go once it enters the tool, does the vendor store it, train on it, or delete it after the session. This is the question most teams skip, and it's the one that matters most for tier 3.

Legal's job is exposure: contracts, data privacy language, anything touching member consent. Negligible for tier 1, core for tier 3.

None of this needs a standing monthly meeting. A shared form works: marketing fills in the use case and tier, IT and legal get pinged only when the tier calls for it. Tier 1 never reaches their inbox. Tier 3 always does.

## What agent files add to the picture

I've been reading through the emerging work around [AGENTS.md](https://agents.md/) and similar agent-targeted instruction files, documents that tell an AI agent what it's allowed to do on a site or system: which endpoints to call, which actions are available, what the rate limits are, and what happens when a call fails. Wix calls their version an [agentic llms.txt](https://www.wix.com/studio/ai-search-lab/llms-txt-files-for-agents). The naming hasn't settled, but the intent is consistent across all of them: point an agent not just at what a system says, but at what it can do.

That's useful for the reasons I wrote about in my agentic-readiness series. It's also a governance problem I hadn't fully accounted for in the framework above, because everything in that framework assumes a centaur relationship, to borrow [Cory Doctorow's term](https://locusmag.com/feature/commentary-cory-doctorow-reverse-centaurs): a staff member drafts something, a person reviews it, a person publishes it. The human stays in control, the tool just moves faster. The tiers and the review process are built around content generation with a human still in the loop before anything happens.

An agent that can read an AGENTS.md file and act on it collapses that relationship. It can register someone for a program, submit a form, update a record, based on instructions it found in a file that may or may not have been reviewed the way the tools in our registry are reviewed. The review step disappears. IT and legal end up doing the reverse-centaur work instead, untangling what an agent already did, after the fact, rather than approving what a person was about to do.

**Two things about the framework change.**

**Registry addition: flag agent-capable tools.** A tool that only writes text and a tool that can submit a form on a member's behalf are not the same risk, even if they're built by the same vendor and used by the same department. The registry needs a column, or at least a flag, for whether a tool is agent-capable, meaning it can take an action rather than only produce a draft a person checks.

**Tier addition: re-evaluate for autonomy, not just data.** A tier 1 tool that starts offering an agentic mode, letting it act without review, should get re-evaluated before that feature goes live internally, not after someone finds out it's already being used that way. The risk tiers need to account for autonomy, not just data sensitivity. The review process I described treats IT's job as checking the data path. For agent-capable tools, IT also needs to check the action path: what can this thing actually do once it's pointed at our systems, and who signed off on that.

The registry, the tiers, and the review process still do the job they were built for. They just need one more question added to each: what data does this touch, and can this thing act on its own once it's set up.

That's the gap I'm building toward closing next, going through our current tool list and re-scoring anything that's picked up agentic features since we first logged it. If your organization has a registry already, that's a fast afternoon of work. If it doesn't, this is as good a place as any to start one.
