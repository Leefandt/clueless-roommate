# Clueless Roommate

> A Claude Code skill that turns "I think I understand this" into "okay, explain it to someone who doesn't."

The agent role-plays a roommate who has never taken your course: curious, forgetful, and confidently wrong. You give a complete explanation first; they take notes, then cross-examine the weak points one at a time — until you can explain the idea in plain language they can restate, exemplify, and correct.

This is the Feynman technique with a pulse. No quiz UI, no visible grading — just a confused roommate who keeps asking "why?"

**How it avoids the usual quiz trap:** you explain the whole thing first, uninterrupted. The roommate's questions are anchored to your own words, and the attack list is finite — so the conversation cannot drift and it has a clear end.

**中文版：[无能的室友.skill](README.zh-CN.md)** · The Chinese version is named exactly **无能的室友.skill**.

## Why it works

- **Feynman technique**: if you cannot explain it, you do not know it.
- **Generation effect**: producing an explanation beats re-reading.
- **Misconception discrimination**: catching a plausible-but-wrong restatement is harder than recalling a definition.
- **Low exam anxiety**: the roommate does not grade or praise you, so the gaps show up without the pressure.

## Demo

```text
You:      I've got it — quiz me.
Roommate: Okay, don't worry about me for a second. Take 5-10 minutes and explain this whole thing — from "why sample variance divides by n-1" to "when it holds" — as if I've never seen it. Say "done" when you're finished.
You:      (a complete explanation, skipping anything you get stuck on)
Roommate: Done? ... Okay, I wrote down a few things. One at a time. You said "the data are always closer to their own mean" — give me actual numbers; is every point closer?
...
Roommate: Okay, I think I've got the gist. Go do your thing; I'll digest it.
```

Then the skill steps out of character and gives a short, honest debrief: **Solid / Mostly solid / Still shaky**, separating what you explained on your own from what you only explained after being asked.

## Four roommate levels

You choose at intake. The default is the purest Feynman mode.

| Level | Who they are | What it trains |
|---|---|---|
| **1. Completely clueless** (default) | Zero background; you must translate every term | Standard Feynman: explain it like a person |
| **2. Knows a little** | Some related background, a few terms | Precision, distinguishing similar concepts, conditions |
| **3. Pretends to understand** | Says "got it, got it" while actually lost | Teaching closure: verify the student really understood |
| **4. Pretends not to understand** | Actually knows the material, plays dumb to test you | Rigor under pressure, anti-complacency; reveal at the end |

Start with 1. Use 3 to practice checking whether a student really understood. Use 4 when you want to be challenged.

## Install

Requires [Claude Code](https://claude.com/claude-code).

Prefer a zip? Download the latest [release](https://github.com/Leefandt/clueless-roommate/releases/latest).

### English version

```bash
git clone https://github.com/Leefandt/clueless-roommate.git
cp -r clueless-roommate/clueless-roommate ~/.claude/skills/
```

Or use a symlink so updates are picked up automatically:

```bash
ln -s "$(pwd)/clueless-roommate/clueless-roommate" ~/.claude/skills/clueless-roommate
```

### Chinese version

```bash
git clone https://github.com/Leefandt/clueless-roommate.git
cp -r clueless-roommate/zh-CN/无能的室友.skill ~/.claude/skills/
```

The Chinese skill is named exactly **无能的室友.skill** in both its folder and `SKILL.md`.

Start a new Claude Code session after installing.

## Usage

1. Send the material (PDF, PPTX, DOCX, images, or markdown) and say **"explain this section"** or **"just quiz me."**
2. If you ask for an explanation, listen, then say **"I got it."**
3. The roommate asks for a complete teach-back. Explain the whole thing (5-10 minutes); if you get stuck, skip it; say **"done."**
4. Then they cross-examine you one question at a time. Answer normally.
5. Stuck? Say **"pause."** Want to switch? Say **"skip."** Done? Say **"stop."**

Trigger phrases: `roommate mode`, `roleplay my roommate`, `I get it — quiz me`, `prove I actually understand this`, `Feynman me`.

### Controls

| Say | What happens |
|---|---|
| `pause` / `break character` | Step out, explain the current point, then ask whether to resume |
| `skip` | Switch to another attack point |
| `skip the teach-back` | Give at least a 3-sentence overview, then go straight to cross-examination |
| `stop` | End and debrief |
| `harder` | More misconception traps and boundary questions, fewer hints |
| `gentler` | More concrete examples and one extra hint |
| `change the level` | Switch among the four roommate levels |
| `change the setup` | Change the roommate's name / personality / major |
| `continue last time` | Resume from the latest session file |
| `don't log` | Do not write a session file |
| `no debrief` | End with one line, no verdict |

Progress is written to `~/roommate-sessions/` by default.

## How it works

```text
0 Intake → 1 Explanation (optional) → 2A Complete teach-back → 2B Cross-examination → 3 Debrief
```

- **2A Teach-back**: you explain the topic uninterrupted. The roommate takes notes and builds a finite **attack map**: coverage, gaps, errors, contradictions, boundaries.
- **2B Cross-examination**: they attack the map one question at a time, always quoting your own words or naming a core concept you never mentioned. They stop when the map is exhausted, after 12-18 questions, or when you stop.
- **3 Debrief**: the verdict separates what you explained spontaneously from what you only explained after being asked (`prompted`).

The core design constraint: **the roommate can tell "I don't follow," but cannot tell "you're wrong."** They never lecture, never correct you, and never reveal a score during the dialogue. Their confusion is the diagnostic signal. If you can get a confused person to actually understand, you probably understand it yourself.

The hidden rubric has two layers:

```text
S (spontaneous, from the teach-back):
0 not mentioned / 1 name or definition only / 2 explains why or gives an example / 3 why + example + condition

D (defended, after cross-examination): 0-3 on the evidence table

F = D, flagged spontaneous / prompted / unresolved.
Solid requires every core concept S >= 2 and D >= 2.
If a concept was only explained after asking, the best verdict is "Mostly solid."
```

## Repo layout

```text
clueless-roommate/                 # English skill (installable)
  SKILL.md
  references/
    persona.md
    knowledge-levels.md
    question-ladder.md
    mastery-rubric.md
    examples.md
    session-template.md
zh-CN/
  无能的室友.skill/                # Chinese skill (installable)
    SKILL.md
    references/...
README.md                          # English (primary)
README.zh-CN.md                    # Chinese
LICENSE
```

## License

MIT. See [LICENSE](LICENSE).
