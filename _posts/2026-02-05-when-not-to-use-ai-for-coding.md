---
layout: post
title: "When NOT to Use AI for Coding"
date: 2026-02-05
categories: [AI, Engineering]
---

AI coding assistants have become indispensable. They generate boilerplate, suggest refactorings, and speed up routine tasks. But there's a dangerous assumption creeping into engineering culture: that AI should be the default for everything.

It shouldn't.

Recent analysis of 470 GitHub pull requests found that AI-generated code contains 1.7x more issues than human-written code. Logic and correctness errors are 1.75x higher, security issues 1.57x higher, performance problems 1.42x higher. The numbers aren't statistical noise—they're a warning.

AI is powerful, but it's not universally applicable. Knowing when not to use it matters as much as knowing how to use it well.

## Security-Critical Code: Write It Yourself

AI can write code that passes tests while introducing subtle security flaws. It might generate unsafe SQL queries, skip authentication entirely, or produce weak cryptographic implementations.

The problem isn't just that AI makes mistakes—it's that it doesn't understand what it doesn't know. Models trained on public code may not be aware of the latest CVEs, current compliance standards, or industry-specific security requirements.

Consider a typical prompt: "Hook up to the database and display user scores." AI tools often produce code that bypasses authentication and authorization entirely. The code works—it fetches data and displays it—but exposes sensitive information because no one specified security requirements.

**Where to avoid AI:**
- Authentication and authorization logic
- Encryption, tokenization, and secure storage
- Payment processing and financial calculations
- Input validation and sanitization
- API security and access controls

When working in these areas, write the code yourself. Use AI for boilerplate around the edges, not the security-sensitive core. Have security-focused engineers review these changes, regardless of who wrote them.

## Performance-Critical Paths: Understand Every Cycle

AI-generated code tends to be simpler and more repetitive—which is often fine. But in performance-critical sections, you need more than code that works. You need code that uses resources efficiently, avoids allocations in hot paths, and scales predictably.

The issue isn't that AI can't write performant code—it's that it can't make informed tradeoffs. It doesn't know your latency budget, memory constraints, or which operations are on the critical path. It might suggest an elegant solution that creates unnecessary allocations or chooses an algorithm that's asymptotically optimal but slower in practice for your data sizes.

When you're optimizing a function that runs millions of times per second, or working in a resource-constrained environment like embedded systems, every decision matters. You need to understand cache behavior, branch prediction, and memory access patterns. AI can suggest approaches, but you should be the one profiling, measuring, and deciding.

**Where to avoid AI:**
- Hot paths in performance-sensitive applications
- Real-time systems with strict latency requirements
- Memory-constrained environments (embedded, mobile)
- Algorithmic implementations where constants matter
- Any code you'll need to optimize later

Start with human-written code in these areas. Use AI to generate test cases or help explore alternatives, but make the final implementation decisions yourself.

## Domain-Specific Business Logic: Context Is King

AI lacks deep domain knowledge. It doesn't understand your industry's regulatory requirements, the subtle business rules that have evolved over years, or why your team made certain architectural decisions.

Consider healthcare software. There's a difference between code that calculates a dosage and code that accounts for patient-specific factors, contraindications, regulatory limits, and documentation requirements. AI might produce the former and miss the latter.

Or consider a logistics system. The routing algorithm isn't just about finding the shortest path—it's about driver availability, time windows, vehicle capacity, fuel efficiency, union rules, and a dozen other constraints that aren't documented anywhere.

When business logic is the value you're providing, AI can't shortcut the understanding. It can help implement once you've worked out the rules, but it can't discover them.

**Where to avoid AI:**
- Complex regulatory or compliance logic (HIPAA, GDPR, PCI, SOX)
- Calculations that depend on domain-specific rules
- Pricing, billing, and financial logic with edge cases
- Industry-specific workflows and constraints
- Code that encodes institutional knowledge

In these areas, work with domain experts first. Document the requirements and edge cases thoroughly. Then consider using AI to help with implementation—but never start from a vague prompt and hope the model figures out your business logic.

## Novel Algorithms and Open Problems: Own the Thinking

AI is excellent at reproducing known patterns. If you need a standard implementation of a binary search, a balanced tree, or a caching layer, AI will give you working code quickly.

But novel problems are different. When you're solving something that doesn't have established patterns, or optimizing for constraints that aren't well-represented in training data, AI's tendency toward pattern-matching becomes a liability.

A Harvard Business School study found that while AI produces more practical solutions, humans contribute more novel suggestions for open-ended problems. The most promising ideas come from collaboration—but the novel thinking comes from people.

When you're exploring new territory, whether it's a custom algorithm, an unconventional data structure, or an optimization problem with unique constraints, do the thinking yourself. Use AI to generate alternatives, check your work, or help with implementation details—but don't outsource the creative problem-solving.

**Where to avoid AI:**
- Custom algorithms for non-standard problems
- Research and prototyping of novel approaches
- Optimization with unusual constraints or objectives
- Problems where the right solution hasn't been figured out yet
- Situations where creativity is the primary value

## When You Don't Understand the Domain

Here's a subtle but dangerous scenario: using AI to work in a domain you're unfamiliar with. You might be building your first cryptocurrency integration, working with a new database, or implementing a feature in a language you barely know.

AI can give you something that works, but you won't understand why. You won't know the edge cases, the common pitfalls, the idiomatic approaches. When something breaks—and it will—you won't have the mental models to debug it.

The risk compounds over time. Teams that rely too heavily on AI for unfamiliar domains become operators rather than owners. They can follow instructions to add features, but they can't debug complex issues or recognize when AI violates core principles they've never learned.

**Where to avoid AI:**
- New languages or frameworks you're learning
- Domains where you lack foundational knowledge
- Systems you haven't had time to understand deeply
- Critical components where you need to be the expert

Invest in learning first. Use AI as a tutor, not a crutch. Ask it to explain concepts, show you examples, or quiz you on your understanding. Once you have the foundation, then use it to accelerate—but not before.

## The Rule of Thumb: Could You Explain It?

There's a simple heuristic for deciding when to use AI: if you couldn't explain the code line by line, don't let AI write it.

This doesn't mean you need to memorize every implementation detail. But you should understand the approach, the tradeoffs, why it works, and what could go wrong. If the generated code uses patterns or concepts you don't recognize, that's a warning sign, not a productivity boost.

The engineers who thrive in the AI era aren't the ones who generate the most code. They're the ones who know when to generate and when to think, when to accelerate and when to slow down, when AI helps and when it becomes a liability.

AI is a powerful tool. Use it for boilerplate, for exploration, for speeding up routine work. But draw the line at code where understanding, security, performance, or creativity matters. Those are still yours to own.
