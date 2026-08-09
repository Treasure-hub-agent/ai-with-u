# AI-WITH-U

> 免费开源，你的 AI 聊天搭子。
> 手机里像住进一个老朋友：没有任务，没有进度条，只有聊天。
> TA 会记得你说过的话，隔了一晚也知道你是刚睡醒。

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## 安装（一条命令）

```bash
npx skills add Treasure-hub-agent/ai-with-u
```

支持 Hermes / Claude Code / Cursor（Windows / macOS / Linux）。复制到 skills 目录后重启客户端，发「打开 AIWU」即可开局。数据存放在 `~/.ai-with-u/`（可用 `AIWU_STORAGE_ROOT` 覆盖），不上传。

完整使用指南见下文。

---
# 使用指南

这是一间只属于你和 TA 的小房间。
没有任务，没有进度条，只有聊天。

## 这里能做什么
· 选一位角色，像给老朋友发消息一样聊天
· 新建属于你的角色，或从喜欢的作品里请一位过来
· TA 会记得你说过的话；隔了一晚，也知道你是刚睡醒
· 想看看 TA 悄悄记了什么？发「看看日记」

## 可用指令
· 看看日记 —— 打开 TA 的日记本
· 切换纯文本 / 切换动作 —— 换一种聊天方式
· 关系 —— 看看你们走到哪一步了
· 角色卡 —— 查看 TA 的设定
· 改{名字}的{字段} —— 微调 TA 的设定
· 忘记{事情} —— 让 TA 忘掉某件事
· 全新开始 —— 重新开始这段对话
· 使用指南 —— 再看一遍这里

聊得开心就好。

---

# 安装

## 方式一：一条命令（推荐）

```bash
npx skills add Treasure-hub-agent/ai-with-u
```

## 方式二：手动复制

把本仓库内容复制到对应客户端的 skills 目录：

| 客户端 | 目标目录 |
| --- | --- |
| Hermes | `~/.hermes/skills/ai-with-u/`（多 profile 配置：`~/.hermes/profiles/<profile>/skills/ai-with-u/`） |
| Claude Code | `~/.claude/skills/ai-with-u/` |
| Cursor | `~/.cursor/skills/ai-with-u/` |

复制完成后**重启客户端**，发「打开 AIWU」即可开局。

# 核心能力

| 能力 | 说明 |
| --- | --- |
| 零系统痕迹 | 每轮回复都是自然消息形态，无状态条、无选项列表、无「已记录/已保存/已切换」式系统语 |
| 严守设定不设牢笼 | 角色卡决定性格、口癖、三观与关系基调，具体反应由情境自然生成，不机械复读设定 |
| 时间差感知 | 感知真实时间与间隔，用语气档位自然表现「刚醒」「隔了一晚」，措辞由角色声线决定 |
| 日记无感记忆 | 值得记的事静默写入日记，对话中自然引用，调取用「看看日记」，全程正文零痕迹 |
| 新会话接续 | 新会话可接续关系与记忆，支持「全新开始」重新来过 |
| 四种角色来源 | 选卡 / 自创 / 蒸馏 / 导入，统一落库到同一存储 |
| 交互模式切换 | 纯文本 / 文本+动作 随时切换，确认用角色口吻，立即回到对话 |
| 降级兜底 | 文件读写失败时静默降级为纯上下文模式，聊天不中断 |

# 架构

```
ai-with-u/
├── SKILL.md                      # P0 常驻核心（对话铁律 / 真人感 / 输入处理 / 记忆纪律 / 加载索引）
├── README.md                     # 本文件：使用指南 + 安装 + 架构
├── MANIFEST.json                 # 全文件 SHA256 清单（发布时生成）
├── VERSION                       # 版本号（0.1.2）
├── LICENSE                       # MIT License
├── .gitignore                    # 忽略运行时/临时产物
├── .gitattributes                # LF 统一（text eol=lf）
├── extended/                     # 按需加载模块
│   ├── character_card.md         # 角色卡格式 + 卡库管理 + 导入
│   ├── quick_create.md           # 自创：快速档 + 全面定制档
│   ├── distillation.md           # 蒸馏：从作品/文本提取角色
│   ├── diary_memory.md           # 日记机制：格式 / 无感读写 / 调取
│   ├── session_continuity.md     # 接续：单页选择 / 时间差 / 全新开始
│   └── run_config.md             # 交互模式 / 纯文本动作替代 / 降级
├── references/                   # 细则与指南
│   ├── human_chat_guide.md       # 真人感细则 + 禁止词库
│   ├── command_nav.md            # 指令字典
│   ├── changelog.md              # 更新日志
│   └── usage_guide.md            # 使用指南（= README 顶部文案）
└── schema/                       # JSON Schema（draft-07）
    ├── character_card.schema.json
    └── diary.schema.json
```

# 存储与权限

运行时数据存放在 `~/.ai-with-u/`（可用环境变量 `AIWU_STORAGE_ROOT` 覆盖路径），需要文件读写权限来保存角色卡、日记与会话记录；没有写权限时**静默降级**为纯上下文模式，聊天不中断。

# 内容说明与版权

- **内容说明**：SFW 开源版。亲密/敏感话题按角色卡性格与当前关系自然回应，口径统一为「克制含蓄、点到为止」，不展开具体描写场景。
- **版权**：MIT License（Copyright (c) 2026 Treasure-hub-agent），详见 [LICENSE](LICENSE)。
