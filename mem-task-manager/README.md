# Mem Task Manager — Claude Skill

A Claude skill that connects your conversations to [Mem.ai](https://mem.ai), letting you
manage your entire task workflow without ever opening Mem manually.

---

## What It Does

Add tasks, check what's on your list, mark things done, clean up completed items, move tasks
between collections, and more — all by just telling Claude in plain language.

| You say | What happens |
|---|---|
| "Add a task to follow up with the team #Work" | Task is appended to your Work task list |
| "What's on my list? #ClientA" | Claude fetches and displays your open tasks |
| "Mark the invoice task as done #Work" | That task is checked off in Mem |
| "Remove the meeting prep task #ProjectX" | Task is deleted after confirmation |
| "Move the contract review to #ClientB" | Task is removed from source, added to destination |
| "Clear completed tasks #Work" | All checked-off tasks are removed after confirmation |
| "Find any tasks about onboarding #HR" | Claude searches within that collection |
| "What collections do I have?" | Claude lists your Mem collections |

---

## Requirements

- A [Mem.ai](https://mem.ai) account
- The **Mem MCP connector** connected to Claude (available in Claude's connector settings)
- Claude skills enabled

---

## Installation

1. Download `mem-task-manager.skill`
2. Open Claude and go to **Settings → Skills**
3. Click **Install Skill** and select the downloaded file
4. Make sure the **Mem connector** is active in your Claude settings

---

## How to Use It

### Specifying a collection with `#keyword`

Always include a `#CollectionName` to tell Claude which Mem collection to work in:

```
Add a task to send the project proposal #ClientWork
What's on my list? #Marketing
Mark the budget review done #Q3Planning
```

Claude matches the keyword to your collection name in Mem.

### No collection? Claude will ask.

If you don't specify a `#collection`, Claude will always ask before touching anything.
This is intentional — see the section on collection isolation below.

```
You:    Add a task to review the contract
Claude: Which collection should I add this to?
You:    #ClientWork
Claude: Added to Task List in the ClientWork collection ✓
```

---

## All Supported Operations

### Add a task
```
Add a task to send the invoice #Work
Remind me to follow up with the vendor #ClientA
Put "review the onboarding doc" on my list #HR
```

Multiple tasks at once:
```
Add these to #Marketing:
- Draft the newsletter
- Review ad copy
- Send campaign summary to the team
```

---

### View your task list
```
What's on my list? #Work
Show me my tasks for #ClientA
What do I still need to do? #ProjectX
```

Claude displays open tasks clearly, with completed ones shown at the bottom.

---

### Complete a task
```
Mark the invoice task as done #Work
I finished the budget review #Q3Planning
Check off the follow-up call #ClientA
```

You don't need to use the exact task wording — Claude uses fuzzy matching to find it.

---

### Remove a task
```
Remove the meeting prep task #Work
Delete the vendor follow-up from my list #ClientA
Take the onboarding review off #HR
```

Claude will confirm before deleting — removals are permanent.

---

### Move a task to another collection
```
Move the contract review task from #ClientA to #Legal
```

Claude will confirm both the source and destination before making any changes, and ensures
the task only exists in one place afterward.

---

### Clear completed tasks
```
Clear completed tasks #Work
Clean up my list #ClientA
Remove all the finished items #ProjectX
```

Claude counts the completed tasks and confirms before removing them.

---

### Search for a task
```
Find any tasks about onboarding #HR
Do I have anything about the invoice on my list? #Work
Where did I put that task about the contract? #ClientA
```

---

### List your collections
```
What collections do I have?
Show me my Mem collections
```

---

## How Collections and Task Lists Work

**Collections** are folders in Mem that group related notes. Each collection typically
represents a client, company, project, or area of focus. The `#keyword` you use maps
directly to a collection name in Mem.

**Task List notes** are notes inside a collection that hold your to-dos. Claude recognizes
notes with titles like:
- `Task List`
- `Task List Week Ending 5/9`
- `[Name]'s Task List`
- `[Name]'s Daily Task List`

If multiple task list notes exist in a collection (e.g., from different weeks), Claude picks
the most recently updated one by default. You can specify a date if you want a specific one.

---

## Why It Always Asks for a Collection

Collections often represent different clients, companies, or completely separate contexts.
Sending a task to the wrong collection could mean one client's work ends up on another's list.

To prevent this, the skill enforces a strict rule:

> **Claude will never guess, infer, or carry over a collection from earlier in the
> conversation. You must name it explicitly every time.**

This applies to every operation — reading, writing, completing, moving, everything.
It's a feature, not a limitation.

---

## Task Format

All tasks are stored as Markdown checkboxes, compatible with Mem's native task system:

```
- [ ] Open task
- [x] Completed task
```

Existing note content is never reorganized — Claude only appends new tasks or modifies the
specific lines it's been asked to change.

---

## Troubleshooting

**Claude isn't finding my collection**
Make sure the `#keyword` you're using closely matches your collection title in Mem. Exact
or near-exact matches work best.

**Claude can't find a task list note**
The note title needs to contain the words "task list" (case-insensitive). If your note is
named something different, rename it in Mem, or ask Claude to create a new one.

**The Mem connector isn't working**
Go to Claude's connector settings and confirm Mem is connected and authorized. You may need
to reconnect if your session has expired.

**Claude found the wrong task when completing/removing**
If the task description is ambiguous, Claude will list the matches and ask you to confirm.
If it picked the wrong one, just tell it which one you meant.

---

## Feedback & Contributions

This skill was built for personal and professional productivity and shared openly. If you
improve it or adapt it for your own workflow, feel free to share it forward.
