---
title: "The hreflang tags were correct. Every one of them redirected first."
date: 2026-09-09
categories: [seo]
excerpt: "Two hreflang failures, years apart and worlds apart in resources, both missed for the same reason: nobody checked whether the tags' targets loaded directly or bounced through a redirect first."
---

The Hebrew pages of a rare book dealer's new site were live with `dir="rtl"` missing entirely. Prices and ISBNs ran backward. English author names embedded inside Hebrew titles landed on the wrong side of the sentence, and parentheses opened where they should have closed.

I was put on the site after launch to check it, expensive inventory, the kind of listing that can run into five figures, and RTL never made it into the build.

None of that needed a specialist to catch. Pull the page up next to how Google rendered the same text in a search result, and the mismatch was obvious in seconds.

Hreflang was worse, just quieter. It wasn't there at all, on any of the localized pages.

Missing tags are the easy kind of broken. Grep the source, get zero results, you're done, you know exactly what to fix.

Years later I found a version of the same underlying problem at a company with every resource that agency didn't have.

Meta for Creators publishes its creator success stories in close to 30 languages. [The English version](https://creators.facebook.com/creator-success/gray-davis) of one profile and [its Bengali counterpart](https://creators.facebook.com/creator-success/gray-davis?locale=bn_IN) both carry a full, correctly reciprocal set of hreflang tags.

Both versions also point somewhere they shouldn't. The live URL is `/creator-success/gray-davis`. Every hreflang tag on it, and the canonical tag next to them, points to `/creator-success/gray-davis-alternate`, a URL that 301-redirects straight back to the page you're already on. The Bengali version does the same thing, canonicalizing to `/creator-success/gray-davis-alternate/?locale=bn_IN`, another redirect back to where it started. That held for both locales I checked on this page, out of close to 30 available.

A second creator page shows why that distinction matters. [Tyler Cheri's default page](https://creators.facebook.com/creator-success/tyler-cheri) has the same kind of bug, a wrong path segment this time (`/creators/creator-success/` instead of `/creator-success/`) plus a different wrong suffix (`-alternate-version`), also redirecting back to the live URL. But [the Arabic version](https://creators.facebook.com/creator-success/tyler-cheri?locale=ar_AR) of that same page is correct. Canonical and hreflang both point straight at the real page, no detour.

The pattern is inconsistent: broken on one locale of a page, fine on another locale of the same page, broken in a different specific way on an entirely different page. That's a harder problem than a single bad template value, and it means checking one locale and calling the page verified tells you almost nothing about the rest.

Every one of these still resolves, just through an extra hop. That's what Google's own guidance calls out directly: a canonical or hreflang tag shouldn't point at a URL that redirects. It adds a step a crawler shouldn't have to take, and it's the kind of signal that gets deprioritized or dropped instead of followed cleanly.

The book dealer's site and Meta's platform don't have much in common. Both failures came from the same gap: nobody checked what the tags said against what was on the page. The book dealer's dev team knew the syntax and skipped the reading direction. Meta's system generates syntactically correct hreflang and canonical tags, but whatever's filling in the target URL is producing a different wrong answer depending on the page and the locale, sometimes not wrong at all.

Both failures come down to the same fix: open the rendered page, or view source, and check it against what the tag claims.

That check takes about 20 minutes on a site you haven't audited this way before. View source, pull every hreflang link, and load each one directly, not through a click path, and confirm it resolves without a redirect. Do the same for the canonical tag. A tag that's syntactically correct and reciprocal across every language can still be routing crawlers through an extra hop nobody noticed, and one clean locale doesn't mean the rest are clean too. That's exactly the kind of thing that looks fine until someone actually loads each URL.
