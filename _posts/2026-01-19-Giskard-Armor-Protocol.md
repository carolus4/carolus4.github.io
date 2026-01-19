---
layout: post
title: "Giskard: ARMOR Protocol"
excerpt: A changelog for my personal productivity system with local LLMs, with features for each of the ARMOR shields.
image: "/images/list-page/giskard-armor-protocol.webp"
---


# Giskard: ARMOR Protocol

## A changelog for my personal productivity system with local LLMs

Working better was a major motivation for building [Giskard](https://carolus4.github.io/Building-Giskard/). I wanted to start 2026 taking concrete steps to build resilience into my ways of working, based on this investigation into [tech’s most resilient workers](https://www.lennysnewsletter.com/p/how-techs-most-resilient-workers) (paid link).

I had so many ideas for things I could do differently, and there’s a risk of falling down technology and productivity rabbit holes. 

I took a breadth first approach, going through each ‘shield’ in the ARMOR framework, and identifying small \+ powerful changes I could make in a week. 

![ARMOR Shields](/images/giskard-armor-shields.png)

## A. Adding intentions for autonomy

Autonomy comes from choosing what I’m working on. I wanted to articulate that more clearly in Giskard. I already grouped my tasks automatically based on key words for my ‘intentions’: health, career, and learning. I set these up to make sure I was spending enough time on each of these areas.

I added a full doc for intentions with editable descriptions and a filtered view of tasks. I wrote intention descriptions with one-line answers to: 

- What does it mean?  
- Why does it matter?  
- What should this look like / not look like?  
- Includes: Keywords and examples

*Screenshot: Learning intention*
![Learning intention description Screenshot](/images/giskard-armor-learning-intention.png)

## R. Reflections for rock-solid boundaries

Life will test the boundaries I set, chipping away at them. I wanted a mechanism to strengthen boundaries \- effectively learn from times they didn’t work. I set up an explicit recurring task for weekly reflection, to recalibrate priorities.

On a Monday morning, I automatically run a weekly reflections prompt based on last week’s tasks and my intentions. There’s aggregation, a progress update against my goals, and AI suggestions for what I might do more/less of. 

The local-model only constraint is tough here\! To get good review content for the start of the week, I changed the underlying model to Qwen, which is slower but better at tool calling (in this case, managing data) 

There’s an important mindset shift here: with a slower but more agent-like ‘brain’, I’ve been looking for how giskard can run tasks more proactively.

*Screenshot: My first automatically locally generated ‘Reflect on last week’s task’*

![Locally generated Screenshot](/images/giskard-armor-reflection.png)

## M. Mini-exercise daily for maintenance

Maintenance is challenging; good maintenance has a clear upfront cost, and very diffuse benefits. I like the encouragement \+ accountability approach from Fabulous and Headspace. 

I added a daily exercise task in Giskard. The content is a low stakes template for 10 minutes of activity, which helps me just get started. At the end of the day, if I don't complete the task, it gets archived, and a fresh task is created. 

Here, I’m prompting myself. I don’t have a strict eval, but this version achieves 90%+ success at being active every day:

> \# \[date\] Exercise
> This is maintenance, not a goal.
> Aim for 10+ minutes. Exercise machine, Yoga, or Dance.
> It's important to start. You can stop whenever you want

## O. Other ways of doing things, for original thinking

Feeling stuck, or dreading a task kills momentum. Using the chat interface with Giskard has been a way to bypass that. When I review the LLM response to "What should I do next?", I find it easier to get started, or re-plan.

I made that a background process for each task \- coming up with a list of options for immediate next steps. Prompting for very small steps makes that much more likely for me to get started. The recommended next steps are rarely the ones I’ll go for, but when ‘what next’ is a choice, it encourages divergent thinking, as I naturally ask what else I might do.

Example for “Explore integrations for automatic exercise tracking”  
![](/images/giskard-armor-next-step-ideas.png)

## R. Reusable Templates for Role Architecture

For repeated tasks, it helps to iterate on some common building blocks. My approach for similar tasks should be similar \- or evolve as I go. For example, if I organise a meetup every month, I should be able to easily tell what steps to take next month. In the short term, being able to build on top of past tasks avoids re-work; in the medium term, execution can be that much smoother. 

The minimalist approach here was to use hard coded task templates. I found that the local models were struggling with an open ended task breakdown, so I used claude to scan through my past tasks and extract potential templates. I then used a standard template ui, which creates a very simple starting point:

![](/images/giskard-armor-templates.png)

## In Conclusion: building resilience with structured context

Looking back, each feature here is some form of structure in ways of working that I’m choosing for myself. That alone is empowering, like a self help book framework can be, but I’m really interested in how this approach also builds a rich history that I can use to continue improving over time.