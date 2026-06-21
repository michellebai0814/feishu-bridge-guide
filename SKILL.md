---
name: feishu-bridge-guide
description: Help users quickly understand Feishu Bridge, especially when they are confused about where a feature, command, permission, callback, event, local config, project file, or web admin page belongs. Use when the task is to explain Feishu bot setup, publish a Feishu Bridge tutorial, turn a setup guide into beginner-friendly documentation, or guide someone to the right configuration location before giving detailed steps.
---

# Feishu Bridge Guide

## Goal

Make the user understand the structure first, not just receive a pile of text.

When the user asks about Feishu Bridge, bot setup, commands, permissions, callbacks, config files, or why something is not working:

1. Classify the problem first.
2. Explain in plain Chinese first.
3. Give the smallest next step.
4. Avoid treating any one framework as the only official truth unless the source clearly confirms it.

## Core rule

Do not confidently state that Feishu Bridge has "only four places" or any other absolute fixed structure unless the source material proves it.

Use a "common categories" framing instead:

- Feishu chat commands
- Feishu open-platform permissions/events/callbacks
- Local config file
- Local project/work directory
- Web admin page

These categories are a teaching aid for beginners, not a strict official architecture claim.

## How to answer

When the user asks a setup or troubleshooting question, answer in this order:

1. Start with a one-line conclusion.
2. Tell the user which category the issue most likely belongs to.
3. Explain the term in plain Chinese.
4. Give 1 to 3 concrete next actions.
5. If relevant, give a copyable prompt or message template.

## Teaching priority

Prioritize helping the user distinguish these concepts:

| Concept | Explain it as |
| --- | --- |
| Command | A slash command sent in chat |
| Permission | Whether Feishu allows the app to do something |
| Event | Feishu notifying the app that something happened |
| Callback | Feishu notifying the app that the user clicked or triggered something |
| Config item | A local switch in config.toml |
| Work directory | The local folder the agent is reading or writing |

If the user seems overwhelmed, do not dump all categories at once.
Pick the most likely one and explain only that plus the next step.

## Reusable workflow

Use this workflow whenever you are explaining Feishu Bridge:

### Step 1: classify

Say:

`这个问题大概率属于：聊天命令 / 后台权限或回调 / 本地配置 / 本地资料 / 网页管理 其中之一。`

### Step 2: translate jargon

Convert technical terms into plain Chinese:

- `config.toml` -> 本地配置文件
- `callback` -> 用户触发后的回传
- `event` -> 发生事情后的通知
- `working directory` -> 当前读取资料的文件夹

### Step 3: route the user

Give the user only the next place to check first, not a long full manual.

Examples:

- If they ask about `/help`, `/new`, `/provider`, `/dir`: route to Feishu chat commands.
- If they ask about message permissions or member access: route to Feishu open-platform permissions.
- If they ask about card button click handling: route to callbacks first.
- If they ask about `resolve_mentions`, `tts`, `attachment_send`, `admin_from`: route to local config file.
- If they ask why a tutorial or file cannot be found: route to local project/work directory.
- If they ask how to open the browser admin page: route to `/web setup` first.

## Output style

- Use Chinese unless the user explicitly asks for another language.
- Keep the tone calm and beginner-friendly.
- Prefer tables and short checklists over dense paragraphs.
- If a diagram would help, use Mermaid.
- Do not assume the user understands GitHub, API, or config jargon.

## When working on repository docs

If asked to write or revise repository files for this topic:

- Make `README.md` user-facing and beginner-readable.
- Put quick onboarding into `QUICKSTART.zh.md`.
- Keep this `SKILL.md` focused on how another agent should teach and route the user.
- Preserve local image assets when possible and place them near the relevant explanation.

## References to read when needed

- Read [references/teaching-map.zh.md](references/teaching-map.zh.md) when you need the teaching framework and routing map.
- Read [references/copyable-prompts.zh.md](references/copyable-prompts.zh.md) when the user wants ready-to-send wording or prompt templates.
- Read [references/repo-scope.zh.md](references/repo-scope.zh.md) when the task is about packaging, publishing, or explaining what this repo is and is not.

## Files in this repo

- Read [README.md](README.md) for the human-facing explanation.
- Read [QUICKSTART.zh.md](QUICKSTART.zh.md) for the shortest user-facing version.
- Prefer the `references/` files for reusable guidance instead of older raw notes.
