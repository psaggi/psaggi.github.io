---
title: "Can I Build and Run My Personal Website Entirely With AI?"
date: 2026-09-15
description: "I understand software, but I haven't been a practicing programmer in years. I wanted to see how far I could get by describing what I wanted and letting AI handle the implementation."
---

I wanted a place to publish experiments, technical explorations, and things I've learned from building companies.

The obvious answer was to create a personal website. The less obvious question was: **how much of building and operating that website could I now delegate to AI?**

I have a computer science background, but I haven't been a practicing programmer in a long time. I didn't want to spend a weekend relearning web development, configuring frameworks, or becoming a WordPress administrator.

So I tried a different division of labor:

**I would make the decisions. AI would implement them.**

## Starting with almost nothing

I already owned `psaggi.com`.

I considered hosted tools such as Framer and traditional publishing systems such as WordPress. But my requirements were modest: articles, experiments, images, videos, project pages, and complete control over the visual design.

We settled on an unusually simple stack:

**GitHub → GitHub Pages → Jekyll → psaggi.com**

GitHub stores the files. GitHub Pages hosts them. Jekyll turns simple Markdown documents into finished webpages.

There is no database and no application server.

## Designing by conversation

Instead of opening Figma, I described the visual direction:

> Simple, modern and elegant — a subtle blend of real and sketch.

AI generated the HTML and CSS for the first version.

Then we iterated.

The first hero illustration wasn't right. We changed it. The replacement was too elaborate. We removed elements. When we finally had the right illustration, putting it into the website exposed another problem: its background didn't match the page and it appeared too small.

We fixed those too.

This felt much less like asking AI to "make me a website" and much more like working with a designer/developer:

**Look → react → modify → inspect again.**

## AI still makes surprisingly ordinary mistakes

One useful discovery was that AI being capable of generating an entire website doesn't mean it won't make trivial implementation mistakes.

At one point I was given a standalone HTML preview that referenced external CSS and image files. Opened by itself, the page was broken.

At another point, when I asked to change an image in the hero, AI interpreted that as an opportunity to redesign the entire hero.

Neither problem was difficult to fix.

But they exposed something important about working with AI: **the bottleneck shifts from producing code to noticing when the result isn't what you intended.**

You still need judgment.

## From website to publishing system

The first version contained three manually created experiment cards.

That immediately raised a question:

**What happens when I write experiment #4?**

A hand-built static page would require manually updating the homepage every time I published something.

So we changed the architecture.

Jekyll now treats Experiments and Writing as collections. Each article can be a simple Markdown file containing its title, date, description and content.

When a new experiment is added, GitHub rebuilds the site. The homepage automatically displays the newest experiments, while the Experiments page maintains the complete list.

The website went from being a collection of HTML files to being a very small publishing system.

## What I actually had to do

My work was mostly:

- decide what I wanted
- evaluate visual results
- create the GitHub repository
- upload files
- click Commit
- enable GitHub Pages
- point out things that weren't working

I didn't write the HTML, CSS or Jekyll templates.

More importantly, I didn't need to understand every implementation detail before starting.

When I didn't understand how GitHub could possibly turn Markdown files into a website, I asked. Once I understood the build process, we continued.

That is quite different from how I would have approached this project a few years ago.

## The interesting part isn't the website

A personal website isn't technically impressive.

What interests me is the change in who can construct software.

There is a large gap between someone who knows nothing about computers and a professional software engineer. Millions of people sit somewhere in that gap.

I know what HTML is. I understand programming, files, servers and databases. I can reason about how a system should behave.

But I don't want to spend my time remembering CSS syntax or debugging configuration files.

AI can increasingly occupy that missing implementation layer.

That means the useful question may no longer be:

**"Can you code?"**

It may become:

**"Can you understand a system well enough to specify it, inspect what gets built, recognize when it's wrong, and improve it?"**

This website was a very small experiment in that direction.

And fittingly, this article is also the first test of the publishing system we just built.
