# 🧠 Claude Skills

A personal collection of custom skills built for [Claude](https://claude.ai) — each one designed to unlock a specific capability or push the quality of Claude's output well beyond its defaults.

Skills are loaded into Claude's context to give it sharper instructions, better aesthetic judgment, and domain-specific workflows for tasks it handles frequently. Think of them as standing operating procedures that make Claude significantly better at the things you actually use it for.

---

## Skills

### 📄 [letter-page-design](./letter-page-design/)

A skill for generating **print-ready, US Letter-sized (8.5×11 inch) HTML designs** — flyers, handouts, one-pagers, brochures, event programs, spec sheets, and multi-page documents. The core insight behind this skill is that Claude designs *dramatically* better in HTML and CSS than in any drag-and-drop tool like Canva. With the right instructions, Claude can produce editorial-quality layouts with precise typography, CSS Grid compositions, custom print stylesheets, and multi-page structures that would take real effort to replicate manually — and the output is a real file you own, not locked inside a platform. This skill enforces quality standards: distinctive font pairings, CSS variable-driven color systems, proper safe-margin handling, and no generic AI aesthetics. The result is polished, print-ready HTML that exports cleanly to PDF straight from the browser.

---

## How Skills Work

Each skill lives in its own folder and contains a `SKILL.md` file — a structured prompt that Claude reads before tackling a task. The skill defines when to apply itself, what rules to follow, what assets to start from, and what quality bar to hit.

To use a skill, it needs to be installed in your Claude environment so Claude can access it at the start of a relevant conversation. Refer to [Anthropic's documentation](https://docs.claude.ai) for how to set up custom skills.

---

## Structure

```
/
├── README.md                  # This file
└── letter-page-design/
    ├── README.md              # Skill-specific documentation
    ├── SKILL.md               # The skill definition Claude reads
    └── assets/
        └── template.html      # Base template for letter-size designs
```

---

*More skills added as they're built and tested.*
