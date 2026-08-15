# AI-WITH-U

> **AI-WITH-U v0.1.3** — open source. Your AI chat companion.
> It feels like an old friend living in your phone: no tasks, no progress bars, just conversation.
> It remembers your conversations — and knows you just woke up when you message it the next morning.

🌐 **[中文](README.md) | English**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-0.1.3-orange.svg)](VERSION)

---

## ✨ What It Does

**AI-WITH-U** is a companion-chat skill for AI agents — once installed, the AI texts you like a real person. No status bars, no option lists, no robotic assistant voice. Just natural conversation.

**What you get:**

- 💬 **Zero system traces**: every reply reads like a natural message — a real person texting, not customer support answering tickets
- ⏰ **Time-gap awareness**: it knows you just woke up after a night apart, or asks how the last few days have been after a longer silence
- 📔 **Effortless diary memory**: details worth remembering are automatically logged to a diary and referenced naturally in conversation; send "看看日记" (see diary) to view its notes
- 🎭 **Four ways to bring a character in**: derive one from a work you love, create your own, use a character card, or import a local card
- 🔄 **Continue across sessions**: switch clients and pick up right where you left off; "fresh start" anytime
- 🔓 **Open source**: MIT License, all data lives on your own machine

---

## What's New (v0.1.3)

- 📖 **More ways to bring a character from a work**: name a work, upload a text file, paste a passage, give a link, or let the AI fetch context online (links read directly; proactive fetching always asks first)
- 💬 **Actions separated from dialogue**: actions/moods marked with 「(action)」 brackets, clearly distinct from spoken lines
- 📚 **Richer character roster**: import local cards in one step; delete characters you no longer want (card only by default, memories kept); edit diary entries in place
- 📔 **Smarter diary memory**: mood entries stored individually (appended, never overwritten); "forget {thing}" deletes only the matched entry; when unsure, it records nothing — no fabricated information

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
You: 刚醒，早上好

TA: 早呀～ 昨晚梦到什么了？头发都翘起来了，先去喝口水吧。

You: 梦到我们去看海了

TA: （笑）那就当预演咯。等哪天真的去，我要在沙滩上写你的名字。

---

You: 看看日记

TA: 📔 08-10 晴
- 她梦到和我去看海
- 说好了以后要去看真的海
```

*Note: dialogue defaults to Chinese; you can switch to English by telling your character your preferred language.*

---

## Install (one command)

```bash
npx skills add Treasure-hub-agent/ai-with-u
```

Works with Hermes / Claude Code / Cursor (Windows / macOS / Linux). Copy to your skills directory, restart the client, and send "打开 AIWU" (open AIWU) to begin.

> No `npx skills`? See "Manual copy" below.

### Manual copy

| Client | Target directory |
| --- | --- |
| Hermes | `~/.hermes/skills/ai-with-u/` (multi-profile: `~/.hermes/profiles/<profile>/skills/ai-with-u/`) |
| Claude Code | `~/.claude/skills/ai-with-u/` |
| Cursor | `~/.cursor/skills/ai-with-u/` |

Restart your client after copying, then send "打开 AIWU".

---

## Quick Start

1. Load the skill in your agent client (`npx skills add` or manual copy)
2. Send "打开 AIWU" → character selection screen
3. Pick a character: from the roster / create your own / derive / import
4. Chat like you'd text an old friend — it replies in the character's voice
5. Send "看看日记" anytime to see what it quietly noted; "使用指南" for the full command list

> Out of the box, no configuration needed; if file write access is missing it silently degrades to pure-context mode — conversation never breaks.

---

## Commands (English aliases)

All commands currently default to Chinese. English aliases are on the roadmap; until then, tell your character in plain words what you'd like — or use the aliases below where noted.

| Command (default) | English alias | What it does |
| --- | --- | --- |
| 看看日记 | see diary | open its diary |
| 切换纯文本 / 切换动作 | text mode / action mode | switch chat style |
| 继续 | continue | resume the last conversation |
| 关系 | relationship | see where you two stand |
| 角色卡 | character card | view the character's card |
| 改{name}的{field} | edit {name}'s {field} | fine-tune the card |
| 忘记{thing} | forget {thing} | make it forget something |
| 改日记{content} | edit diary {content} | edit a diary entry in place |
| 删除{角色名} | delete {character} | remove a character from the roster |
| 全新开始 | fresh start | start this conversation over |
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
| 💫 Interaction modes | Pure-text / text+action switch anytime; confirmations use the character's voice, then return to conversation |
| 🛡️ Graceful degradation | If file I/O fails, silently falls back to pure-context mode — chat never breaks |

---

## Storage & Permissions

Runtime data lives in `~/.ai-with-u/` (override with env var `AIWU_STORAGE_ROOT`). File read/write is required to persist character cards, diaries, and session history; without write access it **silently degrades** to pure-context mode — chatting never breaks.

---

## Architecture

```
ai-with-u/
├── SKILL.md                      # P0 core (conversation rules / human feel / input handling / memory discipline / loading index)
├── README.md                     # this file: guide + install + architecture
├── MANIFEST.json                 # SHA256 manifest of all files (generated at release)
├── package.json                  # npm release metadata
├── VERSION                       # version number (0.1.3)
├── LICENSE                       # MIT License
├── .gitignore                    # ignores runtime/temp artifacts
├── .gitattributes                # LF normalization (text eol=lf)
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
| Multi-message rendering (`||`-separated) | ⚠️ Optional | Falls back to blank-line separation; separators never leak as visible characters |
| Time-gap awareness | ⚠️ Optional | Uses time-of-day greetings; never outputs "gap detected" system-speak |

---

## FAQ

**Q: How is this different from a regular prompt?**
A: A regular prompt is a suggestion; AI-WITH-U is hard rules + a self-check list. Zero system traces, time-gap awareness, and diary memory all have enforced per-reply checks.

**Q: Where does my chat data go?**
A: Nowhere. All data stays on your machine in `~/.ai-with-u/` (configurable via `AIWU_STORAGE_ROOT`).

**Q: Version history?**
A: See `references/changelog.md`; `VERSION` file and SKILL.md frontmatter are authoritative.

---

## Content & License

- **Content**: SFW open-source edition. Sensitive topics are answered naturally according to the character's card and current relationship, with a consistent "restrained and subtle, to the point" stance — no explicit scenes.
- **License**: MIT License © 2026 Treasure-hub-agent. Free to use, modify, distribute. See [LICENSE](LICENSE).
