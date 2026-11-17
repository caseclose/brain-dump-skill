# brain-dump

> 和 agent 聊着聊着，目标和计划就自己列好了。

一个零摩擦的 Agent Skill：你只管想到啥说啥，agent 负责归类、拆解、提炼待办，每轮把全貌照回给你看。**不用填表、不用组织语言、不用先「开记录」。**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 为什么

正经的项目管理工具要求你先想清楚再写下来；但很多时候你根本还没想清楚，只是脑子里飘着几件事。brain-dump 反过来：**先说，再看，再补**。

第一轮你可能只丢过来几个词：

```text
1. 推理加速调研
2. 训练数据管线
3. 季度汇报
4. 报销
```

几轮之后，它长成了一张带子线、步骤、待办和待确认项的全貌表——这些结构不是你写的，是聊出来的。

回显的意义不只是存档：看到「原来我要干这些」，你才会继续补充。「梳理」就发生在这个「说 → 被整理 → 看见 → 再说」的循环里。

## 安装

需要支持 Agent Skills 的客户端（Claude Code / Codex / Cursor / DeepSeek Harness 等）。

```bash
# personal skill（所有项目可用，推荐）
git clone https://github.com/caseclose/brain-dump-skill.git ~/.agents/skills/brain-dump

# 或放到项目里，只在这个仓库生效
git clone https://github.com/caseclose/brain-dump-skill.git .agents/skills/brain-dump
```

> 路径以你的客户端为准：Claude Code 常用 `~/.claude/skills/`，Codex / DSH 常用 `~/.agents/skills/`。把含有 `SKILL.md` 的目录放进去即可。

也可以只复制 `SKILL.md` 和 `examples.md` 两个文件——**不需要任何脚本或依赖**。

## 使用

**直接用就行，没有命令。**

```text
你：最近在做的主要是：推理加速调研、训练数据管线、季度汇报、报销
agent：已归到 4 个主题，当前全貌如下…（并写入记录文件）

你：调研那块，先测一下 A/B 效果
agent：已挂到「推理加速调研」下，加了 1 条待办…
```

- 说「停 / 别记了」即停用。
- 说「整理出来 / 完整版」给完整整理结果。
- 说「做完了 / 改主意了」→ 改状态，不新增条目。
- 记录默认写在 `BRAINDUMP.md`；若工作区已有 `对话记录.md` 等同类文件，会直接沿用。

## 设计原则

| 层 | 内容 | 默认 |
|---|---|---|
| L0 | 想到啥说啥 → 归类 → 回显全貌 → 落盘 | 永远开 |
| L1 | 待办 / 待确认提炼、状态标记 | 开，但静默 |
| L2 | 已完成态、收盘小结、定时提醒、周报 | **按需才开** |

评判标准不是「记录多完整」，而是「用户多打一个字算我输」。详见 [SKILL.md](SKILL.md) 与 [examples.md](examples.md)。

## 常见问题

**会不会在普通对话里乱写文件？**
靠「记录文件是否存在」门控：工作区没有记录文件、你也没表达记录意图时，就是普通对话；单句随口带过也不会凭空创建文件。

**和 todo / AGENTS.md 有什么区别？**
todo 是单次任务的执行追踪；AGENTS.md 是项目常态约束；brain-dump 是一套可复用的「边聊边整理」工作流，状态全在记录文件里，跨会话可续。

**隐私？**
所有内容只写在你本地工作区的文件里；skill 不联网、不上传、不带脚本。

**能改文件名和格式吗？**
能。改 `SKILL.md` 的「文件」与「文件结构」两节，或第一次就让 agent 按你的格式建。

## License

MIT — 见 [LICENSE](LICENSE)。
