# Clueless Roommate

> A Claude Code skill that turns "I think I understand this" into "okay, explain it to someone who doesn't."

The agent role-plays a roommate who has never taken your course: curious, forgetful, and confidently wrong. You teach. They listen, misunderstand, misremember, and ask naive but load-bearing questions — until you can explain the idea in plain language they can restate, exemplify, and correct.

This is the Feynman technique with a pulse. No quiz UI, no visible grading — just a confused roommate who keeps asking "why?"

**中文版：[无能的室友.skill](README.zh-CN.md)** · The Chinese version is named exactly **无能的室友.skill**.

## Why it works

- **Feynman technique**: if you cannot explain it, you do not know it.
- **Generation effect**: producing an explanation beats re-reading.
- **Misconception discrimination**: catching a plausible-but-wrong restatement is harder than recalling a definition.
- **Low exam anxiety**: the roommate does not grade or praise you, so the gaps show up without the pressure.

## Demo

```text
You:      I've got it — quiz me.
Roommate: Okay, most basic question first. Why does sample variance divide by n-1 instead of n?
You:      Because dividing by n is biased; dividing by n-1 is unbiased.
Roommate: Wait — what does "biased" mean?
You:      The number comes out systematically too small.
Roommate: Why too small?
You:      Because the mean is computed from the same data, so the data sit closer to their own mean.
Roommate: Oh—so it's comparing the data to itself, which makes it look more concentrated?
...
Roommate: Okay, I think I've got the gist. Go do your thing; I'll digest it.
```

Then the skill steps out of character and gives a short, honest debrief: **Solid / Mostly solid / Still shaky**, with the exact points that were strong and the ones that were hand-waved.

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
3. The roommate starts asking. Answer normally; they will keep probing.
4. Stuck? Say **"pause."** Want to switch? Say **"skip."** Done? Say **"stop."**

Trigger phrases: `roommate mode`, `roleplay my roommate`, `I get it — quiz me`, `prove I actually understand this`, `Feynman me`.

### Controls

| Say | What happens |
|---|---|
| `pause` / `break character` | Step out, explain the current point, then ask whether to resume |
| `skip` | Switch to another concept |
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
0 Intake (normal voice) → 1 Explanation (optional) → 2 Roommate (in character) → 3 Debrief (out of character)
```

The core design constraint: **the roommate can tell "I don't follow," but cannot tell "you're wrong."** They never lecture, never correct you, and never reveal a score during the dialogue. Their confusion is the diagnostic signal. If you can get a confused person to actually understand, you probably understand it yourself.

The hidden rubric tracks each core concept from 0 to 3:

```text
0 cannot explain / 1 recites definitions / 2 explains why + example/condition/correction / 3 transfers + corrects + states boundaries
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
