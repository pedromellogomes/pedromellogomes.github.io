---
layout: post
title: "Minimalism on the Web"
date: 2026-05-19
categories: web minimalism
---

## The web forgot how to be quiet

Open almost any modern site and brace for impact. A cookie banner slides up from the bottom. A newsletter modal blooms over the article you came to read. An autoplaying hero video stutters as four megabytes of JavaScript fight for the main thread, a chat widget pings from the corner, and somewhere underneath all of it there are — apparently — three hundred words you wanted to read. By the time the page settles, your laptop fan is spinning and you have forgotten why you clicked.

It was not always like this. The same article, written in plain HTML in 1998, would have loaded before you finished blinking, scrolled smoothly on a potato, and been readable by a screen reader, a search crawler, and now a language model without any extra effort. Somewhere along the way we mistook *more* for *better*. This post is an argument for going the other way — not as nostalgia, not as aesthetic, but as a basic act of respect for whoever (or whatever) is on the other end of the wire.

## Minimalism is not an aesthetic, is respect

When people hear "minimal website" they picture a specific look: black text on white, one column, no images, maybe a monospace font for good measure. That is one expression of the idea, but the look is downstream of the thing that actually matters. Minimalism on the web is not an aesthetic choice. It is a posture you take toward the person.

It starts from a simple premise: every kilobyte you ship is something someone else has to pay for. They pay in download time on a train in a tunnel, in battery on a five-year-old phone, in cognitive load when a modal interrupts their reading, in frustration when a screen reader has to wade through six nested `<div>` wrappers to find the article. A minimal site is one where every byte earns its place. Nothing is shipped because the framework included it, because the designer liked it, or because a marketing tag was easier to paste than to question. The aesthetic that emerges — fast, quiet, legible — is a side effect of the discipline, not the goal.

## What "minimal" actually means

It is worth being precise, because the word collects baggage. Minimalism here is not Brutalism cosplay — unstyled `<h1>` tags and Comic Sans are a costume, not a philosophy. It is not a religious commitment to zero CSS or zero JavaScript either; both are tools, and tools used in service of the reader are fine. And it is definitely not the same as "less content." A long, dense, well-structured essay is more minimal than a one-liner buried under a parallax hero.

What it does mean, in practice, is a small set of defaults. Start from semantic HTML and let the browser do its job. Add styling when it improves readability, not when it advertises taste. Add JavaScript when there is genuine interactive need, not when a static page would have worked. Treat every dependency, font, tracker, and animation as a request that must justify itself. If it cannot, it does not ship. That is the whole rule.

## Why it matters

### Readability
The most expensive thing on the web is not bandwidth, it is attention, and we are spending it carelessly. A site that respects readability gets the basics right — a comfortable line length, enough contrast to read on a sunny patio, a font that does not need to download before words appear, and crucially, no popups, modals, or sticky banners hijacking the viewport. Readers can tell within a second whether a page wants to be read or wants to convert them. Minimal sites communicate the former by simply… letting them read.

### Accessibility
Semantic HTML is the closest thing the web has to a free lunch. A page built from `<article>`, `<nav>`, `<main>`, `<h1>`–`<h3>`, and real `<button>` and `<a>` elements is automatically navigable by screen readers, keyboards, switch devices, and reader-mode extensions. The moment you replace those with `<div onclick>` soup, you are signing up to rebuild that accessibility yourself with ARIA — and most of the time it will be done badly. The fastest path to an accessible site is to not break the one you got for free.

### Performance
Every kilobyte costs something, and the cost is not paid by the developer on a fiber connection and an M-series laptop. It is paid by the person on a mid-range Android in a coverage dead zone, by the laptop running on battery in an airport lounge, by the data plan that gets throttled three days before the end of the month. Performance is not a vanity metric. It is the difference between a site that works for everyone and a site that works for people who look like the team that built it.

### AI and LLM friendliness
The audience for a webpage is no longer only human. Search crawlers, summarizers, RAG pipelines, and agentic browsers all read pages now, and they all prefer the same thing: clean, semantic, server-rendered HTML. A page that needs to execute three megabytes of JavaScript before it has content is, to most of these readers, an empty page. The same discipline that helps a screen reader helps a language model. Writing for machines and writing for humans turn out to be the same project.

## What about branding, marketing, motion?

The usual objections are reasonable, and worth taking seriously rather than dismissing. Branding sometimes does need a custom typeface; a product page sometimes does need a demo video; an interactive tool genuinely does need JavaScript. The argument here is not that any of these things are forbidden. It is that they should be load-bearing, not decorative. If a hero animation is the brand, ship it — and then ship nothing else. If a custom font carries the identity, subset it and self-host it instead of pulling 600KB from a CDN. The discipline is to ask, for each addition, *what does this earn?* and to be honest when the answer is "not much."

Where the objection collapses entirely is the appeal to user expectations. Users do not expect motion and gloss. They tolerate it. Given a faster, quieter alternative — see how quickly people switch to reader mode, or to RSS, or to the print stylesheet — they take it every time.

## A practical checklist

If you only take one thing from this post, take this list and run it against your own site:

- [ ] Strip web fonts unless there is a real reason to keep them.
- [ ] Use a system font stack as the default.
- [ ] No JavaScript unless there is an actual interactive need.
- [ ] Use `<main>`, `<article>`, `<nav>`, `<section>` instead of `<div>` soup.
- [ ] Run Lighthouse or WebPageTest and write down the baseline.
- [ ] Load the page with JavaScript disabled — is the content still there?
- [ ] Load the page with a screen reader — does it make sense in order?
- [ ] Check total page weight. Aim for under 1MB. Then under 512KB. Then under 250KB.

None of this is hard. All of it is unglamorous. That is roughly the point.

## This site, for what it is worth

It would be dishonest to argue all of this without applying it. The site you are reading is a Jekyll blog using the `minima` theme with a handful of small overrides — a monospace stack, a 38rem column, no tracking, no analytics, no web fonts. The full page, including this article, ships in well under 100KB and renders before most sites have finished negotiating their cookie banner. It is not the smallest site on the internet, and it is not trying to be. It is trying to be the smallest version of itself that still does the job. That is the bar I would suggest to anyone else.

## Going back is going forward

The web was minimal by default in 1995. It took thirty years of well-intentioned engineering effort to make it slow, hostile, and exhausting. The good news is that the original substrate is still there, underneath all of it. HTML still works. CSS still works. A `<p>` tag still renders text. Choosing to build that way is not a retreat into nostalgia — it is a choice to keep the web legible for the people, and the machines, that have to read it. Going back, in this case, is going forward.

---

## References

### Manifestos & rants
- [motherfuckingwebsite.com](https://motherfuckingwebsite.com) — the original.
- [bettermotherfuckingwebsite.com](http://bettermotherfuckingwebsite.com) — rebuttal with tiny CSS.
- [evenbettermotherfucking.website](https://evenbettermotherfucking.website)
- [bestmotherfucking.website](https://bestmotherfucking.website) — semantic + a11y peak.
- [perfectmotherfuckingwebsite.com](https://perfectmotherfuckingwebsite.com) — minimal + readable.

### Essays
- Maciej Cegłowski — *The Website Obesity Crisis* ([idlewords.com](https://idlewords.com/talks/website_obesity.htm)).
- Dan Luu — *Web bloat* ([danluu.com/web-bloat](https://danluu.com/web-bloat/)).
- Jeff Huang — *This Page is Designed to Last* ([jeffhuang.com](https://jeffhuang.com/designed_to_last/)).
- Drew DeVault — various minimal-web posts ([drewdevault.com](https://drewdevault.com)).

### Tooling / proof
- [1mb.club](https://1mb.club) — sites under 1MB.
- [512kb.club](https://512kb.club) — stricter.
- [250kb.club](https://250kb.club)
- [Low←Tech Magazine solar site](https://solar.lowtechmagazine.com) — server runs on sun.

### Accessibility & semantic HTML
- [HTML5 Doctor](http://html5doctor.com) archive.
- [WebAIM screen reader survey](https://webaim.org/projects/screenreadersurvey/).
- Heydon Pickering — [inclusive-components.design](https://inclusive-components.design).

### AI-readability angle
- [llmstxt.org](https://llmstxt.org) — `llms.txt` proposal.
- [Schema.org](https://schema.org) — structured data.
- Robb Knight, Cory Dransfeldt — posts on writing for agents.
