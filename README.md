# Trigger Journal

A small, very private tool for gently capturing triggers and making patterns
visible over time — **without judging and without repairing.**

> What bothers me out there has almost nothing to do with what's out there —
> and almost everything to do with something in me.

The practice: whenever I think "it's out there", I write it down and ask one
single question — **"Are you sure it's out there?"** At the end of the week I
look at which patterns came up.

## The stance (please read this first)

- **There is nothing to fix.** Observe, don't repair. "Let it out."
- **No judgment** — and never reinforce self-judgment. That's why there are
  deliberately **no streaks, no points, no "good/bad" ratings.**
- **Inviting questions instead of answers.** The tone ends on an open question.
- **Maximally private.** Local-first. Nothing gets uploaded.

## Two ways in — same data

Choose freely, depending on the moment. Both write the same format.

### 1. The app (just fill it in, works on your phone)

Open **`app/index.html`** in a browser — a double-click is enough. No
install, no account, works offline.

- Fill in the fields (only **situation + story** are required, the rest is optional).
- If there is a lot of "outside" and the turn is still empty, a gentle
  invitation appears: *"Are you sure it's out there?"* — an invitation, not a
  correction.
- **"Set it down"** saves locally in the browser (localStorage). Nothing
  leaves your device.
- **"Copy this week · for Claude"** puts a ready-made, gentle prompt on your
  clipboard — paste it into Claude (app or Claude Code) and you get the
  weekly reflection.
- **Export / import (.json)** for backups, or to deliberately share your list.
- **Gentle backup nudge:** if a few entries are unsaved (or your last backup
  is more than a week old), a soft question appears asking whether you'd like
  to export — no alarm, "Later" is always available. Protects you from losing
  entries when browser storage gets cleared.

> On a phone: open the file via your files app, or host the repo with GitHub
> Pages and add the page to your home screen.

### 2. The terminal (Claude Code)

If you open Claude Code in the cloned folder, you have two commands (they
live in `.claude/commands/`, so they load automatically):

- **`/trigger`** — Claude walks you gently through an entry and saves it as
  `entries/YYYY-MM-DD-HHMMSS.json`. You can also just start talking.
- **`/week`** — Claude reads the last 7 days of entries and writes the weekly
  reflection: what came up, one suspected pattern, one open question. No
  solution, no advice. This happens entirely locally in the conversation —
  **no API key, no cloud.**

`/week` also reads **app entries**: drop an exported `.json` list into the
folder (or paste your "Copy this week" text into the chat) — it doesn't
matter whether you captured on your phone or in the terminal.

### The lenses for pattern recognition

During the reflection, Claude draws on `reference/lenses.md` — a curated set
of interpretive lenses: the voice in the head, the witness behind it, stored
charge (old imprints — the backbone of "the same root trigger on different
surfaces"), letting through instead of pushing down, the Buddhist *second
arrow* (for the meta-trigger), Byron Katie's "Is that really true?", parts
and roles, Eckhart Tolle's pain-body, Tara Brach's RAIN as a tone, and an
optional Human Design lens (conditioning / not-self). Everything is offered
**as an invitation to notice** — no diagnosing, no fixing.

## Privacy — how sharing works

**You share the tool, never your entries.**

- `.gitignore` excludes the contents of `entries/` and `reflections/`. Your
  intimate data never lands on GitHub. Everyone keeps their own journal locally.
- App entries live in the browser's localStorage — they don't go anywhere either.
- "Giving someone my list" is always a **deliberate** act: tap *Export* in the
  app and pass the file on, e.g. via Signal.

## Data format

One entry (app and terminal identical):

```json
{
  "id": "2026-06-29-201433",
  "timestamp": "2026-06-29T20:14:33",
  "context": "work | relationship | family | other",
  "trigger_outside": "the situation (the outside)",
  "story": "who/what I'm blaming",
  "body": "sensation, location",
  "emotion": "the feeling",
  "identity": ["roles/identities that got touched"],
  "reflection_inside": "where is this in me?",
  "meta_trigger": false
}
```

An example lives in `examples/`.

## Layout

```
trigger-journal/
├─ app/index.html        # the UI for filling in (one file, offline)
├─ .claude/commands/     # /trigger and /week for Claude Code
├─ reference/lenses.md   # interpretive lenses for the pattern recognition
├─ entries/              # your entries (NOT shared, via .gitignore)
└─ examples/             # one example entry
```

---

*This is not a substitute for therapy. It is a tool for self-reflection and
pattern recognition — a companion, not a treatment.*
