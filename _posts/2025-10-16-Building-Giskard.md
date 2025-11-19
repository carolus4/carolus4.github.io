---
layout: post
title: Building Giskard
excerpt: How far can I push AI tools, as a solo builder? I started vibe-coding a todo list, and I’m now building a personal productivity agent, running LLMs locally. 
image: "/images/list-page/building-giskard-dawn.webp"

---
'Todo apps' feel to me like overhead, not support. This summer, I had a look at what's out there with AI, but it was still underwhelming. Rather than another premium subscription, I started experimenting with building my own productivity system, focused on problems that were most important to me personally: the emotional labor of prioritisation, staying intentional with how I spend my time, and simply having a good record of my tasks over time.

Here's a look at what I tried, and some lessons learned along the way.

## “The fast fashion era of SaaS” ([Sam Altman](https://x.com/sama/status/1952084574366032354))

One hypothesis is that if average-quality software or features are cheaper, we'll get a long tail of tools proliferating, and evolving rapidly. 

It’s clear to me that personalized versions of your paid-for SaaS are **very** achievable. The trade off between fewer features and better alignment genuinely feels magical. So my project has a UI, but doens't have WatchOS reminders. You might find todo.txt files and claude code completely cover your use case (like e.g. [Teresa Torres's approach](https://www.linkedin.com/posts/teresatorres_me-to-claude-what-should-i-work-on-next-activity-7380337003957055488-GQmR)).

Here’s a screenshot of what that part looks like today:
![Giskard Task View](/images/building-giskard-tasks.png)

There's one important caveat: I’m building alone, for myself, to get more done but also as a way to explore and learn about what's possible.

## “The tool should get out of your way” ([Karri Saarinen](https://www.sequoiacap.com/article/linear-spotlight/))

As I added features, incremental building and the overhead of task management was getting more laborious. That shifted my perspective, and I started asking how much of the overhead I could offload. 

### Run locally for peace of mind
I started thinking about how LLMs could augment my planning, and I introduced this as a key constraint, because: 
1. Credit anxiety is real on an llm-based service, or if you trust a coding agent with a paid API key. This influences the design, especially for things that should feel like a background hum, like categorising tasks or updating short descriptions. 
2. AI shouldn't replace my thinking. A lot of my tasks include some form of problem solving, and commercial LLMs tend towards average solutions. Being deliberate about the models, prompts, and agent design gives me a sense of control. I think this approach compounds over time. ([see also, why I’m writing]({% post_url 2025-08-18-Why-Write-2025 %}))

Here’s an early version, based on the idea that I want to make sure I’m spending my time intentionally (ie. avoid under-indexing on health and learning, really).

![Giskard Classification Prompt](/images/building-giskard-classification-prompt.png)
![Giskard Classification Log](/images/building-giskard-classification-log.png)

### Detail deep-dive: don’t make me work
Having deep empathy with myself as a user, I’ve removed any attribute editing from the UI. That removes the temptation to be a super user and just get the boring bits done, creating a forcing function to fix the prompts, if there are issues. 

One of the biggest wins here has been learning evaluations from the ground up. I started by rolling my own, with ChatGPT’s help, and it’s been a very helpful way to build up intuition for model performance and prompt-engineering.

## “It’s not prioritisation till it hurts” ([Ami Vora](https://amivora.substack.com/p/simplifying-your-product-strategy))

In all of this, there’s been one really big opportunity - going from task-tracking, to an assistant. Having connected my task database and locally running LLM, I’ve been looking at agent workflows. Simple RAG already has some “wow” moments for me.

### Immediate wins - what would I do if I was in flow?

Here's an example. When I'm in a state of flow, I find it easy to break down a task, progress, re-plan, etc. But if I'm between calls, or starting work on a lazy day, it can take me a while to warm up. I've really like having Giskard as a companion that channels the energy of my best self. 

> (me) I’ve got 30mn, pick a task for me
> 
> (giskard) Okay, I’ve fetched 22 tasks for you! There are a few learning-focused options, like “Evaluating AI Agents course” or “Discover how people are working through todos today?”. There’s also a shorter “Short Run (careful with knee)” if you’re looking for something more active.
>
> Given you only have 30 minutes, I'd recommend “Evaluating AI Agents course” – it seems like a great way to spend a focused 30 minutes learning. Would you like me to go ahead and add that to your to-do list?

![Giskard RAG](/images/building-giskard-rag.png)

The prioritisation pain is real, and sometimes that can lead to procrastination. It feels a bit like the difference between a creative and editing mindset. It’s been nice to offload some of that emotional labour. 

There are non-trivial limitations to running my own local models, especially because it feels like a bunch of extra scope which can slow down iteration. On the other hand, I am looking forward to applying some of the research on getting the most out of these smaller models. 

## Shout if you disagree!

This is an early snapshot of what I'm thinking. There's a lot I'm excited about discovering - if you disagree or have any other recommended readings, please do let me know :)