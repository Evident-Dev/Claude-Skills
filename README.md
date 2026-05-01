# 🧠 Claude Skills

A personal collection of custom skills built for [Claude](https://claude.ai), each one designed to unlock a specific capability or push the quality of Claude's output well beyond its defaults.

Skills are loaded into Claude's context to give it sharper instructions, better aesthetic judgment, and domain-specific workflows for tasks it handles frequently. Think of them as standing operating procedures that make Claude significantly better at the things you actually use it for.

---

## Skills

### 📄 [letter-page-design](./letter-page-design/)

Generates print-ready, US Letter-sized HTML designs including flyers, one-pagers, brochures, multi-page documents, and more. Claude produces better layouts in HTML/CSS than any drag-and-drop tool, and this skill enforces the quality standards to prove it.

---

### ✅ [mem-task-manager](./mem-task-manager/)

Full task management inside [Mem.ai](https://mem.ai) through conversation. Add, view, complete, remove, move, and clear tasks across your Mem collections by referencing any collection with `#collection` syntax. Requires the Mem MCP connector.

---

## How Skills Work

Each skill lives in its own folder and contains a `SKILL.md` file, a structured prompt that Claude reads before tackling a task. The skill defines when to apply itself, what rules to follow, what assets to start from, and what quality bar to hit.

To use a skill, it needs to be installed in your Claude environment so Claude can access it at the start of a relevant conversation. Refer to [Anthropic's documentation](https://docs.claude.ai) for how to set up custom skills.

---

*More skills added as they're built and tested.*
