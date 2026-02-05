---
layout: post
title: "When NOT to Use AI for Coding"
date: 2026-02-05
categories: [AI, Engineering]
permalink: /when-not-to-use-ai-for-coding/
---

AI coding assistants have become indispensable. They generate boilerplate, suggest refactorings, and speed up routine tasks. But there's a dangerous assumption creeping into engineering culture: that AI should be the default for everything.

Here's where AI fails, and where human judgment remains non-negotiable.

## Security-Critical Code

Authentication, encryption, payments, input validation—these aren't places for AI experiments.

Research from CodeRabbit analyzing 470 GitHub PRs found AI-generated code has 1.7x more issues overall, with 1.75x more security flaws specifically. Models often skip authentication entirely, produce hardcoded secrets, or use insecure defaults.

PCI Security Standards Council explicitly recommends limiting AI in authentication modules and financial systems.

The rule: if a mistake here causes data exposure or financial loss, write the code yourself.

## Performance-Critical Paths

Real-time systems, memory-constrained environments, hot paths in applications—these require careful optimization and thorough testing.

AI can produce code that looks correct but has subtle performance issues. Unnecessary allocations, inefficient algorithms, missing edge cases in time complexity—these don't show up in happy-path tests.

Performance tuning requires understanding of the problem space, not just generating working code. Use AI for boilerplate or initial implementations, then profile and optimize yourself.

## Domain-Specific Business Logic

Regulatory requirements, pricing logic, industry-specific workflows—these require domain knowledge that general-purpose models lack.

AI might suggest a pricing calculation that's mathematically correct but violates a compliance requirement. It might generate a workflow that works functionally but ignores industry regulations.

The rule: if the business rules are specific to your domain, validate AI outputs against those rules line by line.

## Novel Algorithms and Open Problems

Custom solutions, research, optimization with unusual constraints—these require creativity beyond what training data provides.

Harvard research shows humans contribute more novel solutions for open-ended problems, while AI excels at practical implementation. When you're solving a problem that doesn't have well-trodden paths, AI tends to produce average solutions that work but don't excel.

The rule: if the problem requires genuine innovation or research, don't expect AI to do the heavy lifting. Use it for implementation, not ideation.

## When You Don't Understand the Domain

New languages, unfamiliar frameworks, systems you haven't mastered—these are risk multipliers.

AI can't catch issues you don't know to look for. If you're unfamiliar with a framework, you won't recognize when AI uses an anti-pattern specific to that ecosystem. You'll ship code that has subtle issues you can't debug.

The rule: if you can't independently verify correctness without spending hours researching, don't ship it.

## The Bottom Line

AI is a tool, not a replacement for judgment. Use it where it excels—boilerplate, refactoring, exploring—but maintain ownership of security, performance, and domain-specific correctness.

The rule: if you couldn't explain the code line by line, don't let AI write it.

Never commit code you don't understand.
