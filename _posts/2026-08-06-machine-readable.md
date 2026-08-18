---
layout: post
title: "Making YMCA Information Machine-Readable"
date: 2026-08-06
categories: [seo]
excerpt: "Sitemaps get you found, schema ensures you're understood correctly once you are — pulling apart two things marketers lump together as 'technical SEO stuff.'"
---

![Structured data or code representing a machine-readable layer over web content](/writing/assets/images/machine-readable.jpg)

A sitemap and a schema tag have two different jobs, but most marketers lump them together as "technical SEO stuff." Let's pull them apart.

An XML sitemap is a list which tells search engines and AI crawlers which pages exist and when they last changed. Just a URL, and a last-modified date, done.

Without one, some pages just don't get found. They're called orphan pages: nothing on the site links to them, so nothing following links ever stumbles onto them. It could be a branch's holiday hours page or an old program flyer. Invisible to anything crawling by link alone.

A sitemap fixes that by providing a list. It doesn't replace good internal linking, but it catches what linking misses.

Schema markup does something different. It's a layer of code that tells a machine what a page actually is, not just what words are on it. This page is a YMCA branch. This one's a swim lesson program, running on a specific date at a specific location.

Without schema, a machine has to infer all of that from context, the way a human would. With it, the machine is told directly.

That's more important than it probably sounds. One structured data company found that adding schema and linking entities correctly cut down on a bank's branches being confused with wrong locations in AI answers. Ambiguous names, shared with other places, kept getting misread. Telling the machine explicitly which entity was which fixed it.

YMCAs have this exact problem. Go to [ymca.org](http://ymca.org/) and lookup branches named "Downtown," "Central," or even "Jefferson." Without much work you can also find program names that repeat across associations with slightly different meanings each time. A person reading the page in context sorts that out without thinking. A system trying to match an entity to an answer doesn't have that context to lean on.

One last point here: schema has to match what's actually on the page. If your markup says a class meets Tuesdays and the visible page says Wednesdays, that mismatch (sometimes called schema drift) teaches the system not to trust your data.

Sitemaps get you found, and schema ensures you're understood correctly once you are. Neither is new and both deserve a real audit rather than an assumption that they're already in place.

Post 4 in a series on what AI agents mean for websites. Post 3 covered the UX fundamentals that help both agents and humans. Next: llms.txt, and why it's worth watching but not overselling.
