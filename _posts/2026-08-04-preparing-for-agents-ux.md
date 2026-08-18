---
layout: post
title: "Preparing for Agents Starts With Better User Experience"
date: 2026-08-04
categories: [seo]
excerpt: "None of this requires new technology — the accessibility work that's been on every audit checklist for a decade is exactly what makes a site usable by AI agents."
---

![A robot or AI agent icon interacting with a web page interface](/writing/assets/images/agents.jpg)

None of this requires new technology, most of it's just good practice that's gone unfinished.

AI agents rely heavily on something called the accessibility tree. It's the same underlying structure that screen readers use to help blind users navigate a page. Right-click a button on your site, choose Inspect, open the Accessibility tab, and you'll see exactly what an agent sees. If your "Register" button shows up as a generic, nameless box, that's the problem.

A lot of the work that makes a site usable for an agent is the same work that makes it usable for a person with a disability, or really, for anyone in a hurry.

**Clear, descriptive buttons.** Not "Learn More" five times on one page, but something that tells you what happens when you click it.

**Form fields with real labels**, not placeholder text that vanishes the second you start typing. An agent that sees a blank box with faded gray text can't tell an email field from a name field once you start typing.

**Stable layouts.** If a button jumps an inch down the page because a banner loads late, a person recovers without noticing. An agent that already identified a click target at a fixed spot doesn't. It clicks where the button used to be.

**Content that doesn't depend on JavaScript finishing** before it appears. Plenty of sites load the price or the CTA only after a script runs. Some agents render that JavaScript fully. Many don't, to save time. If it only shows up after the page finishes loading, an agent reading the raw page source never sees it.

**Making "Request Information" and "Schedule an Appointment" impossible to miss** (I've been advocating for this on our mental wellness pages,) instead of buried under three paragraphs of program description. That's aimed at people who are already anxious and don't want to hunt for the next step. An agent needs the same clarity: a CTA it can identify without guessing is one it can act on.

**Modals that open mid-flow.** Maybe a "confirm your session" step or a consent screen appears, and the agent doesn't register that the page underneath it just changed. It keeps trying to act on a page that isn't there anymore.

This is all about accessibility and clean UX, the stuff that's been on every website audit checklist for a decade. None of it is agent-specific advice. The difference now: it costs you an entire category of traffic that can't route around bad design the way a person can instead of just frustrating a few visitors.

Post 3 in a series on what AI agents mean for websites. Post 1 covered the shift from AI search to AI agents. Post 2 covered why ranking, being cited, and being usable are three different things. Next: making program and location data machine-readable.
