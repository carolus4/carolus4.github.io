---
layout: post
title: Building Giskard
excerpt: How far can I push AI tools, as a solo builder? I started vibe-coding a todo list, and I’m now building a personal productivity agent, running LLMs locally, with full prompt transparency. 
image: "/images/building-giskard-dawn.png"

---
How far can I push AI tools, as a solo builder? I started vibe-coding a todo list, and I’m now building a personal productivity agent, running LLMs locally, with full prompt transparency.

## “The fast fashion era of SaaS” ([Sam Altman](https://x.com/sama/status/1952084574366032354))

I’m building alone, for myself, to learn faster, and get more done.

I wanted to vibe-code a todo app for myself. As someone who thinks deeply about how things get done, I looked at linear, todoist and other tools, and I realised I could de-scope these massively to meet just the things I care about.

It’s clear to me: personalized versions are **very** achievable. This comes with fewer features, but better alignment with my preferred ways of working. Your mileage may vary; for example getting reminders on a smartwatch was completely out of scope, or maybe something like todo.txt files and claude code completely cover your use case (e.g. [Teresa Torres's approach](https://www.linkedin.com/posts/teresatorres_me-to-claude-what-should-i-work-on-next-activity-7380337003957055488-GQmR)).

Here’s a screenshot of what that part looks like today:
![Giskard Task View](/images/building-giskard-tasks.png)

## “The tool should get out of your way” ([Karri Saarinen](https://www.sequoiacap.com/article/linear-spotlight/))

As I added features, incremental building and the overhead of task management was getting more laborious. That shifted my perspective, and I started asking how much of the overhead I could offload. 

## Run locally for peace of mind
I started thinking about how LLMs could augment my planning, and I introduced this as a key constraint, because: 
1. Credit anxiety is real on an llm-based service, or if you trust a coding agent with a paid API key. This influences the design, especially for things that should feel like a background hum, like categorising tasks or updating short descriptions. 
2. AI shouldn't replace my thinking. A lot of my tasks include some form of problem solving, and commercial LLMs tend towards average solutions. Being deliberate about the models, prompts, and agent design gives me a sense of control. I think this approach compounds over time. I pull the same thread in my update on why I’m writing

Here’s an early version, based on the idea that I want to make sure I’m spending my time intentionally (ie. avoid under-indexing on health and learning, really).

![Giskard Classification Prompt](/images/building-giskard-classification-prompt.png)
![Giskard Classification Log](/images/building-giskard-classification-log.png)

### Detail deep-dive: don’t make me work
Having deep empathy with myself as a user, I’ve removed any attribute editing from the UI. That removes the temptation to be a super user and just get the boring bits done, creating a forcing function to fix the prompts, if there are issues. 

One of the biggest wins here has been learning evaluations from the ground up. I started by rolling my own, with ChatGPT’s help, and it’s been a very helpful way to build up intuition for model performance and prompt-engineering.

## “It’s not prioritisation till it hurts” ([Ami Vora](https://amivora.substack.com/p/simplifying-your-product-strategy))

In all of this, there’s been one really big opportunity - going from task-tracking, to an assistant. Having connected my task database and locally running LLM, I’ve been looking at agent workflows. Simple RAG already has some “wow” moments for me.

Here’s an example:
> (me) I’ve got 30mn, pick a task for me
> 
> (giskard) Okay, I’ve fetched 22 tasks for you! There are a few learning-focused options, like “Evaluating AI Agents course” or “Discover how people are working through todos today?”. There’s also a shorter “Short Run (careful with knee)” if you’re looking for something more active.
>
> Given you only have 30 minutes, I'd recommend “Evaluating AI Agents course” – it seems like a great way to spend a focused 30 minutes learning. Would you like me to go ahead and add that to your to-do list?

![Giskard RAG](/images/building-giskard-rag.png)

The prioritisation pain is real, and sometimes that can lead to procrastination. It feels a bit like the difference between a creative and editing mindset. It’s been nice to offload some of that emotional labour. 