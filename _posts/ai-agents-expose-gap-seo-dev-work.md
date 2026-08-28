---
layout: post
title: "AI agents expose a gap between SEO and dev work. Marketing should own it."
categories: [martech, seo]
permalink: /ai-agents-expose-gap-seo-dev-work/
---

![acx](/assets/images/acx.jpg)

The SEO industry can't agree on a name for what happens after an AI agent lands on your site. Some call it ASO, Agentic Search Optimization. Others call it ADO, Agentic Discoverability Optimization. Neither term is settled, and neither is a good pick. ASO already belongs to App Store Optimization. ADO has meant Azure DevOps to developers for years, and before that it meant ADO.NET. The naming confusion is a symptom of a bigger problem: the industry doesn't fully understand what this layer is or who's supposed to own it.

The split most SEOs already work with is technical, content, and links. Technical covers crawlability and site speed. Content covers keywords and structure. Links are backlinks and directory listings. That framework held up fine for twenty years, then AI search showed up and added two more things to track.

AEO and GEO cover getting cited inside an AI-generated answer instead of ranking a blue link. In practice this means schema markup, FAQ-formatted content, and writing in a way a language model can lift cleanly into a summary. Broadly, you're optimizing to get recommended, not just found.

ASO and ADO, as the industry currently uses them, cover the technical layer underneath an agent that's ready to act. Clean APIs. Checkout flows that don't assume a human is clicking through them. This is infrastructure work, and it sits with developers the way server response time always has.

Three categories: getting found, getting recommended, and being technically transactable once an agent decides to act. On paper, that looks like a complete pipeline.

Someone asks an AI agent to find Sunday morning swim lessons for their 6-year-old and sign her up. This is a fair test of the pipeline, because it touches all three categories and then keeps going past where they stop.

First, discovery. The agent searches, reads a handful of local sites, and picks a candidate: a YMCA branch with a swim program. This is AEO and GEO doing exactly what they're supposed to do. The branch showed up and got cited.

Second, the agent has to find the actual schedule. Sunday morning, ages 5 to 7, open slots. If that information is buried in a PDF, hidden behind a class-finder widget that only renders after three clicks, or dumped into a table with no semantic structure, the agent is now guessing instead of reading. This isn't a discoverability failure, the site already got found. It's not an infrastructure failure either, there's no API to be clean or dirty yet.

This already happens. Wix's AI Search Lab has documented agents getting completely stuck on cookie consent banners, blocked by a dismissible pop-up a human clears without a second thought. Nothing in the current taxonomy owns that failure either.

Third, assume the agent gets past that and finds a registration form. Multi-step, dynamic fields that load after a dropdown selection, a CAPTCHA halfway through. A human parent would grumble and push through. An agent can lose its place entirely, or submit something wrong because a field it needed hadn't rendered yet when it tried to read the page.

Fourth, if the form goes fine, there's a waiver. Medical release, liability language, a checkbox the agent needs to interpret and act on correctly, not just click past.

Fifth, payment. This is where ASO/ADO-as-infrastructure finally kicks back in: a clean, agent-readable checkout either completes the transaction or it doesn't.

Two ends of this process are covered. The middle isn't. Dashboards aren't tracking how many agents got a class schedule wrong, or gave up on a form, or dropped the whole task at step three. This gap sits outside search and outside infrastructure.

This needs a name. My first instinct was ACO, Agent Conversion Optimization, since it matches the family, everything else in this mess ends in "Optimization." Except ACO already means something. Ant Colony Optimization is a real, decades-old technique in computer science: ants and pheromone trails, shortest-path problems solved by simulated insects. Enough readers here may have hit it in a CS course that using ACO would just be planting a second landmine next to the one ADO already stepped on.

So: ACX. Agent CX. Anyone in SEO, marketing, or web design already knows CX, customer experience, it's a new subject standing in front of old vocabulary. I'm aware that's still one more acronym in an industry glutted with jargon. I don't have a better answer.

ACX sits between AEO/GEO and ASO/ADO on purpose. Discovery gets an agent to your site. Infrastructure lets it complete a transaction once it's decided to. ACX is everything in between: whether the agent can actually read your schedule, get through your form, and finish the task it showed up to do. No existing tool tracks it. Google Search Console doesn't. The AI-citation trackers agencies are building for GEO don't either. A technical SEO audit won't catch it, since nothing about it is broken infrastructure. We've revealed a gap in the funnel, invisible for lack of anyone measuring it.

The argument against ACX having a home in marketing usually goes like this: this is a technical problem, not a marketing one. Marketing does keywords, positioning, and copy. Getting an agent through a broken form or a mis-rendered schedule is an engineering fix, so it should sit with engineering.

There's a version of this argument that sounds reasonable, mostly because it's been made before, about a different layer. For years, technical SEO got waved off the same way, crawl budgets and site speed, all filed under "that's a dev thing" by marketers who never learned it. But a slow page load is just conversion abandonment dressed like a rendering bug. The fix being in a codebase never let marketing off the hook.

Calling ACX a dev problem makes the same mistake, just louder. It's not just underestimating how much of the technical layer marketing already has to own, it's misclassifying the failure entirely. A broken API is an infrastructure problem. An agent that gets lost in a four-step form, or misses a schedule trapped in a badly structured table, is failing because the experience is bad. That's the same problem as bad typography: the information was technically present, but it wasn't designed to be usable by whoever, or whatever, showed up to read it. Calling that a dev problem is like calling comic sans on a pitch deck an artist's problem instead of a marketing one.

When an AI agent navigates a website, it isn't reading pixels. Most agentic browsers, including Playwright MCP, the standard tool for browser automation, work off the accessibility tree: a structured map of the page built from ARIA attributes and semantic HTML, the same map screen readers have used for years. OpenAI has said as much directly, ChatGPT Atlas uses ARIA tags, the same labels and roles that support screen readers, to interpret a page's structure. An unlabeled button, a form field with no associated label, these fail a screen reader user but they also fail an agent the same way, and for the same reason.

Accessibility has never been "just a dev problem." It's had a home in marketing, UX, legal, and compliance for years, because ADA lawsuits and WCAG audits made sure of it. That argument, that accessibility belonged entirely to engineering and could be ignored everywhere else, never held up. So when the infrastructure agents depend on turns out to be the exact same infrastructure accessibility has been maintaining all along, the "this is new, hand it to the devs" argument is wearing a false moustache. The layer already has an owner. It's been sitting in marketing's lap the whole time.

Devs build the pipes. Marketers design what happens inside them, what triggers a visitor, human or otherwise, to actually complete the thing they came to do. That's the same job description CRO has had for two decades, aimed at a visitor who doesn't have eyes or patience but does have a task to finish.

Start with value proposition. An agent evaluating a swim program doesn't read your homepage the way a parent does, it summarizes and compares. If your pricing and schedule are contradictory across pages, or locked inside an image instead of text, the agent doesn't penalize you for it. It just moves on to the next candidate that answered the question cleanly. It's a value proposition failure, the same kind a human would hit too, given less patience than curiosity.

Then trust. A parent looking at a swim program checks the cancellation policy and whether the instructors are certified. An agent checks the same things, because it's evaluating on the same criteria a cautious human would, just faster and without the benefit of a gut feeling. If that information exists on the page but sits three scrolls down, past a slider and two testimonials, neither the parent nor the agent finds it in time to matter.

Then friction. Humans abandon carts because a checkout has too many steps, or asks for information it already has. Agents abandon sessions for the same reason, just with a shorter fuse. A CAPTCHA it can't solve, a script that renders content half a second too late for its context window to catch, a form that resets after a wrong click, all of it reads as friction, and friction is the one thing conversion-rate work has spent twenty years learning to strip out.

These are the same failures CRO has always existed to catch, just aimed at a visitor that gives up efficiently instead of angrily.

Companies chasing ACX are optimizing the wrong end of the store. They're polishing the checkout counter, clean APIs, fast payment rails, while the aisles leading there stay a chaotic maze: unreadable schedules, dead-end dropdowns, trust signals placed where no visitor, human or otherwise, would actually see them. A checkout counter doesn't matter if no one makes it that far.

Marketers have owned the layout of that store for as long as there's been a store. The visitor walking through it just changed. It still notices the same things: whether the shelves make sense, whether it can find the exit without asking for help. That job doesn't need a new acronym. It's the same one it's always been, aimed at someone new.
