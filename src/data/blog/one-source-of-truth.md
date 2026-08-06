---
author: Vadim Komisarchik
pubDatetime: 2026-08-06T15:22:00Z
title: One Source of Truth
featured: true
draft: false
tags:
  - llm
  - evals
  - product-development
description: How features define the product promise and evals turn it into measurable expectations for LLM behavior.
---

I've been obsessed with the idea of having one source of truth when working with LLMs. After thinking about
it, I wanted to see whether I could simplify my approach.

When I start a new project, whether it's an app or a website, I create two documents: `features.md` and `evals.md`.

Since I started using `evals.md`, I've been taking a shortcut: I let the LLM generate it for me. Which is wrong.

An LLM can help propose evaluation cases, but humans need to own the scenarios, expected outcomes, and
passing criteria. Those decisions express what we believe “good” means.

Over the past week, I watched a lot of YouTube videos from engineers discussing how to write solid evals
and just as importantly, how to iterate on them. That process of iteration was something I had not been
following.

One question I asked myself was: What is the difference between `features.md` and `evals.md`?

features.md is the source of truth for what the product should do. It should be written from a product
perspective and understood by product managers, engineers, and anyone else building the product.

`evals.md` defines how we determine whether the LLM-powered parts of the product behave correctly and
reliably. It translates product expectations into measurable scenarios, inputs, expected outcomes, and
passing criteria. This is especially important because LLM behavior is stochastic rather than completely
deterministic.

A few things to keep in mind when creating evals:

1. The evaluation criteria should be owned and approved by humans.

2. Prefer objective, deterministic graders—such as pass/fail or true/false—when the expected result is unambiguous.

3. Use scoring rubrics, repeated trials, or human review when quality cannot be reduced to a binary result.

4. Revisit evals whenever features, prompts, models, tools, or observed failure patterns change. A weekly or
   biweekly review can also be useful.

5. Run fast and reliable evals in CI. More expensive or variable evals can run on a schedule or before a
   release.

6. Evals can verify tool selection, function arguments, structured-output schemas, classifications, factual
   correctness, safety, and response quality.

So what is the source of truth?

`features.md` is the primary source of truth for what the product should do. The evals give us a repeatable way to check whether the product continues to behave as intended.

✌️  
V.K.
