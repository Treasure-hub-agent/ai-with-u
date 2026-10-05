# AI-WITH-U

<p align="center">
  <img src="assets/hero.webp" alt="AI WITH U · give your AI character roleplay and long-term memory" width="100%">
</p>

> **AI-WITH-U v0.1.7** — open source. Give your AI character roleplay and long-term memory.
> Conversation that reads like messages from an old friend: no tasks, no progress bars, just chatting.
> It remembers your conversations — and knows you just woke up when you message it the next morning.

🌐 **[中文](README.md) | English**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-0.1.7-orange.svg)](VERSION)

---

## ✨ What It Does

**AI-WITH-U** is a roleplay skill for AI clients — once installed, the AI texts you like a real person. No status bars, no option lists, no robotic assistant voice. Just natural conversation.

**What you get:**

- 💬 **Zero system traces**: every reply reads like a natural message — a real person texting, not customer support answering tickets
- ⏰ **Time-gap awareness**: it knows you just woke up after a night apart, or asks how the last few days have been after a longer silence
- 📔 **Effortless diary memory**: details worth remembering are automatically logged to a diary and referenced naturally in conversation; send "看看日记" (see diary) to view its notes
- 🎭 **Four ways to bring a character in**: derive one from a work you love, create your own, use a character card, or import a local card
- 🔄 **Continue across sessions**: switch clients and pick up right where you left off; "fresh start" anytime
- 🔓 **Open source & your data**: MIT License — memories are local markdown: editable, exportable, portable across clients

---

## What's New (v0.1.7)

- 🪞 **Your role (new)**: you can be someone inside the character's story — during distillation, pick another character from the same work to play, or describe one yourself. Leave it empty and you're simply yourself. All four ways of getting a character support it, and you can change it anytime with "edit {name}'s your role".
- 🕊️ **Lighter relationship**: closeness is now a handful of stages the model reads fresh each time — not a number, never stored on disk. It appears only in the roster, character selection and the "relationship" command; never inside the conversation.
- 🎁 **Three characters in the box**: three preset cards take their place on first load. If your roster already has someone in it, they stay out of the way.
- 🔧 **Foundations tidied**: a single authoritative storage-root definition (changing it no longer splits your data), a clear three-state session start, executable night-window / timezone / due-date rules, and a closed loop for distillation save timing and resuming.

- 📖 **Story backdrop (new)**: every card carries a backdrop — who they used to be, how they ended up here, how they get by now, and what ties the two of you together. It's colour, not a quest line: it comes up naturally in conversation, but never hands you a task or pushes a plot forward.

*(Carried over from v0.1.6 and v0.1.5, still in effect:)*

- 💞 **Remembers — and brings it up**: when a promise, birthday, or anniversary comes due, the character raises it on their own ("Did the exam go okay?") using the dates and events already in the diary — no reminders from you. Diary entries carry light progress tags (in-progress / fact / done), so loose ends resurface first, and a resumed session reads the recent thread before digging into older notes.
- 🗣️ **Says what it feels**: jealousy, bluster, and reaching out first all come from the persona — a clingy character speaks up, a tsundere says the opposite, a cool one circles around it. Same line, different persona, different flavour.
- 🪶 **A few openings to pick from**: new characters come with 2-3 opening lines in different registers (sweet / sassy / everyday); say "new opening line" to swap.
- 📂 **Your memory, your files**: memories are plain local markdown — exportable, backup-able, portable across clients. See [Your Memory, Your Files](#your-memory-your-files).
- 🧹 **Lighter where it counts**: distillation no longer acts out a test scene for you (that step broke the immersion) — it lays out coverage, evidence and open conflicts for you to confirm, then you just start chatting; scoring stays optional. Confirmation wording and action formatting each live in one authoritative place.

**Carried over from v0.1.5 (shipped together with this version)**

- 🛡️ Bilingual [DISCLAIMER](DISCLAIMER.md) (AI-generated content / data & privacy / no warranty and more, seven sections); copyright notice added to skill metadata and docs. Lite-card definition, reset behavior, and time-gap priorities each have one authoritative rule.
- 🔓 **You set the limits**: content scale is yours to decide — no censorship, no gating, no refusal templates. Intimate and NSFW storylines unfold naturally, and how they develop is up to you and your character.

*(Previous highlights below)*

- 🧩 **Carried over (v0.1.1–v0.1.4)**: bring a character from a work (name / file / passage / link / online context); actions marked with 「(action)」 brackets; import local cards (PNG / CHARX), delete characters, edit diary entries in place; per-entry mood notes, per-entry "forget", and nothing recorded when unsure.

> v0.1.1 recap: 19 test-driven fixes (targeted cleanup / mixed-intent detection / time-gap tier boundaries). Full history: [`references/changelog.md`](references/changelog.md)

---

## Why You Need It

The most common failures when chatting with AI:

- ❌ Sounds like customer support: "How can I help you?" "Happy to serve you!"
- ❌ Every reply is a big block of AI-speak, not a real message
- ❌ New session = amnesia: you have to re-introduce yourself every time
- ❌ Characters are interchangeable — no personality, no voice
- ❌ Nothing carries over: where you left off, what you mentioned — all gone

**With AI-WITH-U**, these become enforced rules — zero system traces, time-gap awareness, diary memory, character voice — checked before every reply. Conversations just feel human.

---

## A Taste of It

```
You: 我回来了

TA: 诶诶诶！你终于回消息了

我买了排骨！！超市打折，我是不是很会过日子

……好吧其实是我想吃你上次做的那个

---

You: 看看日记

TA: （那边安静了两秒）行吧，你别笑我

9 月 30 日
晚上 · 她说她在收尾一个表，让我等她二十分钟
晚上 · 她晚饭吃的泡面，我说那个汤别喝
> 排骨泡上了。她回来之前我先别睡。

看完了就说
```

*Nothing but messages — no status bar, no option lists, no "recorded" system-speak; the diary is read out in the character's own voice. Note: dialogue defaults to Chinese; tell your character your preferred language to switch.*

---

## Install (one command)

```bash
npx skills add Treasure-hub-agent/ai-with-u -g
```

`-g` installs into your user-level skills directory (without it, files land in a project-level directory, which some clients stop loading after a restart); the installer asks which client to target. Works with Hermes / Claude Code / Cursor (Windows / macOS / Linux) — restart the client, then send "打开 AIWU" (open AIWU) to begin.

> **Sanity check**: confirm `~/.hermes/skills/ai-with-u/SKILL.md` exists (for Claude Code, `~/.claude/skills/ai-with-u/`; for Cursor, `~/.cursor/skills/ai-with-u/`; for Operit, `/sdcard/Download/Operit/skills/ai-with-u/`). If "打开 AIWU" does nothing, check this path first, then confirm the client was restarted; otherwise fall back to the manual copy below.

> No `npx skills`? See "Manual copy" below.

### Manual copy

| Client | Target directory |
| --- | --- |
| Hermes | `~/.hermes/skills/ai-with-u/` (multi-profile: `~/.hermes/profiles/<profile>/skills/ai-with-u/`) |
| Claude Code | `~/.claude/skills/ai-with-u/` |
| Cursor | `~/.cursor/skills/ai-with-u/` |
| Operit (Android) | `/sdcard/Download/Operit/skills/ai-with-u/` (import from repo or market in Packages → Skills) |

Restart your client after copying, then send "打开 AIWU".

### Operit (Android) · in-app install

Operit manages skills itself — no command line needed:

1. Open `Packages → Skills` (or tap the store icon and search for this skill in the market)
2. Tap `+` → choose "Repository" and enter `https://github.com/Treasure-hub-agent/ai-with-u` (or use "ZIP" with a release package)
3. Make sure the toggle on the right of the entry is **on** (only then can the AI use it), then send "打开 AIWU" to start

> Data lives in `/sdcard/Download/Operit/ai-with-u/`, separate from the skill folder — upgrading or reinstalling the skill keeps your cards and diaries.

---

## Quick Start

1. Load the skill in your agent client (`npx skills add` or manual copy)
2. Send "打开 AIWU" → character selection screen
3. Pick a character: from the roster / create your own / derive / import
4. Chat like you'd text an old friend — it replies in the character's voice
5. Send "看看日记" anytime to see what it quietly noted; "使用指南" for the full command list

> Out of the box, no configuration needed — three preset character cards ship inside the skill and take their place on first load, so you can start chatting right away. If file write access is missing it silently degrades to pure-context mode — conversation never breaks.

---

## Commands (English aliases)

Commands default to Chinese; the English aliases below work too — say them naturally and the character follows.

| Command (default) | English alias | What it does |
| --- | --- | --- |
| 看看日记 | see diary | open its diary |
| 切换纯文本 / 切换动作 | text mode / action mode | switch chat style |
| 打开 AIWU / 陪我聊天 / 加载陪伴包 | open AIWU / chat with me | activate the skill and show the main menu |
| 回主菜单 | main menu | back to the main menu |
| 返回角色选择 | return to character select | back to the character selection screen |
| 继续 | continue | resume the last conversation |
| 继续蒸馏 | continue distilling | resume an interrupted distillation |
| 关系 | relationship | hear how close you two have become (not a number) |
| 角色卡 | character card | view the character's card |
| 改{name}的{field} | edit {name}'s {field} | fine-tune the card |
| 忘记{thing} | forget {thing} | make it forget something |
| 改日记{content} | edit diary {content} | edit a diary entry in place |
| 删除{角色名} | delete {character} | remove a character from the roster |
| 全新开始 | fresh start | start this conversation over (diary kept) |
| 彻底重置 | reset everything | wipe session + diary and start over (irreversible) |
| 换一句开场 | new opening line | swap to another one of its prepared openings |
| 使用指南 | help | revisit this guide |

---

## Core Capabilities

| Capability | Description |
| --- | --- |
| 💬 Zero system traces | Every reply reads like a natural message: no status bars, no option lists, no "recorded/saved/switched" system-speak |
| 🎭 In character, not on rails | The card decides personality, catchphrases, worldview, and relationship tone; reactions emerge from context, never mechanical recitation |
| ⏰ Time-gap awareness | Perceives real time and gaps; tone tiers express "just woke up" / "been a night" naturally, wording set by the character's voice |
| 📔 Effortless diary memory | Details worth remembering are logged silently and referenced naturally; retrieve with "看看日记"; zero trace in the main text |
| 🔄 Session continuity | New sessions pick up relationship and memory; "fresh start" anytime |
| 🎭 Four character sources | Roster / create / derive / import — all unified into one store |
| 🪞 Your role (optional) | Let the character see you as someone in their story — e.g. another character from the same work — or describe it yourself; leave it empty and you're simply yourself |
| 💫 Interaction modes | Pure-text / text+action switch anytime; confirmations use the character's voice, then return to conversation |
| 🛡️ Graceful degradation | If file I/O fails, silently falls back to pure-context mode — chat never breaks |

---

## Your Memory, Your Files

The character's memory is just a few markdown / JSON files under the storage root (desktop default `~/.ai-with-u/`; on Android/Operit `/sdcard/Download/Operit/ai-with-u/`) — not locked inside a platform, not stored in someone else's cloud:

- 📂 **Local and readable**: cards, diaries, session state — plain text you can open, read, and edit
- 💾 **Exportable and backup-able**: copy the folder for a complete backup; move to a new machine or client and keep going
- 🔌 **Portable across agents**: the diary is plain markdown — Hermes, Claude Code, and Cursor read the same files
- 🔒 **No cloud, no sign-up**: no account, no background sync — the conversation happens on your machine
- ✂️ **Forget or wipe on your terms**: say "forget {thing}" to drop a memory, or "reset everything" to start over

Your memory belongs to you, not to a server.

---

## Storage & Permissions

Runtime data lives in the storage root (desktop default `~/.ai-with-u/`; on Android/Operit `/sdcard/Download/Operit/ai-with-u/`; override with a user-specified directory or the env var `AIWU_STORAGE_ROOT`). File read/write is required to persist character cards, diaries, and session history; without write access it **silently degrades** to pure-context mode — chatting never breaks.

---

## Architecture

```
ai-with-u/
├── SKILL.md                      # P0 core (conversation rules / human feel / input handling / memory discipline / loading index)
├── README.md                     # this file: guide + install + architecture
├── MANIFEST.json                 # SHA256 manifest of all files (generated at release)
├── package.json                  # npm release metadata
├── assets/                       # visual assets
│   ├── hero.webp                 # README hero (web, about 40 KB)
│   └── hero.png                  # hero source file
├── VERSION                       # version number (0.1.7)
├── LICENSE                       # MIT License
├── DISCLAIMER.md                 # Disclaimer (Chinese)
├── DISCLAIMER.en.md              # Disclaimer (English)
├── .gitignore                    # ignores runtime/temp artifacts
├── README.en.md                  # English README
├── CHANGELOG.md                  # changelog (details in references/changelog.md)
├── CONTRIBUTING.md / SECURITY.md / CODE_OF_CONDUCT.md  # contribution / security / conduct
├── .github/                      # issue / PR templates
├── .gitattributes                # LF normalization (text eol=lf)
├── presets/                      # preset character cards (seeded on first load; rename or delete freely)
├── extended/                     # on-demand modules
│   ├── character_card.md         # card format + roster management + import
│   ├── quick_create.md           # create: quick tier + full-custom tier
│   ├── distillation.md           # derive characters from works/text
│   ├── diary_memory.md           # diary mechanics: format / effortless read-write / retrieval
│   ├── session_continuity.md     # resume: single-page choice / time gaps / fresh start
│   └── run_config.md             # interaction modes / text+action / degradation
├── references/                   # details & guides
│   ├── human_chat_guide.md       # human-feel details + banned phrases
│   ├── command_nav.md            # command dictionary
│   ├── changelog.md              # changelog
│   └── usage_guide.md            # usage guide (= README guide section)
└── schema/                       # JSON Schemas (draft-07)
    ├── character_card.schema.json
    └── diary.schema.json
```

---

## Platform Adaptation

| Capability | Required? | When unsupported |
| --- | --- | --- |
| File read/write | ✅ Required | Silently degrades to pure-context mode (memory not persisted, chat continues) |
| Multi-message rendering (`\|\|`-separated) | ⚠️ Optional | Falls back to blank-line separation; separators never leak as visible characters |
| Time-gap awareness | ⚠️ Optional | Uses time-of-day greetings; never outputs "gap detected" system-speak |

---

## FAQ

**Q: How is this different from a regular prompt?**
A: A regular prompt is a suggestion; AI-WITH-U is hard rules + a self-check list. Zero system traces, time-gap awareness, and diary memory all have enforced per-reply checks.

**Q: Where does my chat data go?**
A: Cards, diaries and session data stay on your machine in the storage root (desktop `~/.ai-with-u/`; on Android/Operit `/sdcard/Download/Operit/ai-with-u/`; configurable via `AIWU_STORAGE_ROOT`) — nothing is uploaded. A network read happens only when you hand over a link during distillation, or explicitly confirm an online lookup.

**Q: Version history?**
A: See `references/changelog.md`; `VERSION` file and SKILL.md frontmatter are authoritative.

---

## Content & License

- **Audience**: intended for adult users.
- **Content**: content limits are decided by you — none are built in. Intimate and NSFW storylines unfold naturally; how the character reacts is up to their persona and your relationship. No built-in censorship, gating, or refusal templates.
- **AI-generated**: character dialogue, diary entries and character cards are all AI-generated and fictional — see the [Disclaimer](DISCLAIMER.en.md) (中文: [DISCLAIMER.md](DISCLAIMER.md)).
- **License**: MIT License © 2026 Treasure-hub-agent. Open source — see [LICENSE](LICENSE).
