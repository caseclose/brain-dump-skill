# brain-dump

> 随口说，简短记。

把零散想法、待办和进展整理到工作区的 `BRAINDUMP.md`。不填表、不追问；每轮只改相关条目，简短回复变化。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 安装

把仓库放入客户端的技能目录，例如：

```bash
git clone https://github.com/caseclose/brain-dump-skill.git ~/.agents/skills/brain-dump
```

也可安装到项目的 `.agents/skills/brain-dump`；具体路径以客户端为准。无脚本、无依赖。

已通过 Git 安装的可在技能目录运行 `git pull --ff-only` 更新。

## 使用

```text
你：记一下，推理加速先测 A 模型，季度汇报下周准备，还有报销。
agent：已记下这三项。
你：报销交完了。
agent：报销已标为完成。
```

记录保持紧凑：

```markdown
# 记录
- 推理加速：先测 A 模型
- 季度汇报：下周准备
- [x] 报销：已提交
```

- 说「全貌 / 完整版」再展示当前记录；平时只回复变化。
- 说「别记了」停止写入，说「恢复记录」继续。
- 已有同类记录会沿用；普通闲聊不创建文件，查询不改文件。
- 默认不加原话存档、更新日志、逐条时间戳或重复总览。旧存档保留，文件名与格式可直接指定。
- 只整理，不自动执行待办。内容保存在本地工作区。

技能规则见 [SKILL.md](SKILL.md)，更多场景见 [examples.md](examples.md)。

MIT · [LICENSE](LICENSE)
