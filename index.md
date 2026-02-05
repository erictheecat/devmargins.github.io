---
layout: default
---

# DevMargins

Skeptical, operator-first insights on AI and software engineering.

---

## Latest Posts

{% for post in site.posts limit:5 %}
### [{{ post.title }}]({{ post.url }})
<small>{{ post.date | date: "%B %e, %Y" }}</small>

{{ post.excerpt }}

[Read more →]({{ post.url }})
{% endfor %}

---

## About

DevMargins is a blog focused on structural insights about AI-assisted development, avoiding hype, and identifying what's actually worth your attention.

**No fluff. No emojis. No "game-changing" nonsense.** Just honest observations about tools and workflows that shape how we write software today.

---

## Philosophy

### What we believe:

- **Observational > argumentative** — We point out systems and failure modes, not dunk on individuals
- **Structural > hot takes** — Insights that age well in 6 months or we don't publish them
- **Operator-first** — Written for people building things, not talking about building things
- **Credibility > engagement** — We'd rather be right than viral

### What we cover:

- AI coding tools and their real tradeoffs
- Development workflows that actually work
- Supply chain and security in AI era
- Structural issues in how we build software

---

## Contact

Follow on [X (Twitter)](https://x.com/devmargins) for shorter takes.
