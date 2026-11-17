<div align="center">

# AI_Workspace_OS

A sanitized public snapshot of one local AI workspace: the rules it runs by, and the decisions it keeps.

一个脱敏的公开快照：一个本地 AI 工作台的工作规则，以及它留档的决定。

![Files](https://img.shields.io/badge/files-3-informational)
![Stack](https://img.shields.io/badge/stack-none%20detected-lightgrey)
![Snapshot](https://img.shields.io/badge/snapshot-2026--08--13-informational)
![License](https://img.shields.io/badge/license-not%20specified-lightgrey)

</div>

> **How to read this page / 怎么读这页**
> English first, then the same content in Chinese — not a summary, not a separate half.
> 每段英文在前、同一内容的中文紧跟在后；不是摘要，也没有单独的「中文版」。

---

## At a glance · 一眼看懂

| Field · 字段 | Value · 内容 |
|---|---|
| **Problem<br/>问题** | Workspace rules and operational decisions live in one person's head or in old chat logs, so they get re-argued every few months.<br/>工作台的规则和运维决定只存在某个人脑子里或旧聊天记录里，隔几个月就得重争一遍。 |
| **Fix<br/>做法** | Two plain Markdown files — `AGENTS.md` for rules, `MEMORY.md` for decisions — published with the private data stripped out.<br/>两个普通 Markdown 文件：`AGENTS.md` 写规则，`MEMORY.md` 写决定；发布时把私有数据全部剔除。 |
| **Cost<br/>代价** | Nothing to install. Read two files.<br/>不需要安装任何东西，读两个文件即可。 |
| **Not<br/>不是** | Not a framework, not a template, not runnable software.<br/>不是框架、不是模板、也不是可运行软件。 |

## What is in the snapshot · 快照里有什么

Three files and no others, and the count is the point: this repository publishes an operating record, not a codebase.

三个文件，仅此而已；数量本身就是重点：这个仓库公开的是一份运行记录，不是一个代码库。

```text
AI_Workspace_OS/
├── .gitignore   # what stays out of publication · 发布时排除什么
├── AGENTS.md    # working rules for agents in this workspace · 工作台里 agent 的工作规则
└── MEMORY.md    # durable decisions and operations log · 长期决定与运维记录
```

[AGENTS.md](AGENTS.md) declares the project name, the initialization date `2026-07-30`, and the line "Detected stack: none yet". That last line still holds at HEAD: there is no `package.json`, `pyproject.toml`, `go.mod`, or `Cargo.toml` anywhere in the tree.

[AGENTS.md](AGENTS.md) 声明了项目名、初始化日期 `2026-07-30`，以及「Detected stack: none yet」这一行。这行在 HEAD 上依然成立：整棵树里没有 `package.json`、`pyproject.toml`、`go.mod` 或 `Cargo.toml`。

## The rules it runs by · 它按什么规则干活

Six rules from [AGENTS.md](AGENTS.md). Each one is testable by watching a single action, which is why they are short.

[AGENTS.md](AGENTS.md) 里的六条规则。每条都能通过观察一个动作来检验，这也是它们写得短的原因。

| Rule · 规则 | What it means in practice · 实际含义 |
|---|---|
| Inspect real state first<br/>先看真实状态 | Read the machine before changing it.<br/>改之前先读一遍机器。 |
| Shortest reliable path<br/>最短可靠路径 | Reuse an existing install channel instead of adding a parallel one.<br/>复用已有安装渠道，不新增一套平行安装。 |
| Keep changes focused<br/>改动收敛 | Preserve unrelated files and user data.<br/>不动无关文件和用户数据。 |
| Never touch secrets<br/>不碰密钥 | Do not read, print, copy, or store secret values.<br/>不读取、不打印、不复制、不存储密钥值。 |
| English for artifacts<br/>产物用英文 | Code and technical artifacts in English; discussion and summaries in Chinese.<br/>代码与技术产物用英文，讨论与总结用中文。 |
| Verify with a check<br/>用检查验证 | Confirm a version or health check, not just "it installed".<br/>确认版本或健康状态，而不是「装上了」就算完。 |

## What stayed out · 哪些没有被发布

This is a sanitized root snapshot rather than a filtered copy of a larger history. [MEMORY.md](MEMORY.md) records that publication happened on `2026-08-13` from a sanitized root history, and that both a directory scan and a full-history Gitleaks scan passed before publishing.

这是一份脱敏后的根快照，而不是从更长历史里筛出来的拷贝。[MEMORY.md](MEMORY.md) 记录了发布发生在 `2026-08-13`、来源是脱敏的根历史，并且发布前目录扫描与全历史 Gitleaks 扫描都通过了。

The exclusion list itself is in [.gitignore](.gitignore), and it is the most honest part of this page:

排除清单写在 [.gitignore](.gitignore) 里，这是这页最诚实的部分：

| Excluded · 排除项 | Reason · 原因 |
|---|---|
| `.downloads/`, `.tmp/` | Bulk downloads and scratch files are not knowledge.<br/>批量下载和临时文件不算知识。 |
| `.env`, `.env.*` | Credentials never enter public history.<br/>凭据不进入公开历史。 |
| `*.key`, `*.pem` | Private keys are excluded by extension.<br/>私钥按扩展名排除。 |

## Status and limits · 状态与边界

One commit (`5cac9f7`, 2026-08-13), three files, no CI workflow, no package manifest, no tests, no `LICENSE` file. Everything here is documentation; nothing here executes.

一次提交（`5cac9f7`，2026-08-13）、三个文件、没有 CI 工作流、没有包清单、没有测试、没有 `LICENSE` 文件。这里全是文档，没有任何东西会执行。

Known limits, stated rather than hidden:

边界写出来，而不是藏起来：

- The Open Design `0.16.1` install recorded in [MEMORY.md](MEMORY.md) happened on one private machine and is **not reproducible from this repository** — the checksum is logged, the binary is not shipped.<br/>[MEMORY.md](MEMORY.md) 记录的 Open Design `0.16.1` 安装发生在某台私有机器上，**仅凭本仓库无法复现**：记录里只有校验值，没有随仓库发布二进制。
- There is no CI badge above because there is no workflow to point one at. A badge pointing nowhere renders "no status" forever.<br/>上面没有 CI 徽章，因为确实没有可指向的工作流；指向空处的徽章会永远显示 "no status"。
- No license is granted (see the last section), so this is reference material, not something to fork and adopt.<br/>未授予任何许可（见最后一节），所以这是参考资料，不是拿去 fork 采用的东西。
- The "OS" in the name labels this workspace; it is **not** an operating system in the kernel sense.<br/>名字里的 "OS" 只是这个工作台的叫法，**不是**内核意义上的操作系统。
- The workspace itself is not included. You are reading the record of it, not the machine.<br/>工作台本体并不在这里。你读到的是关于它的记录，不是那台机器。

## License · 许可

No `LICENSE` file is present, so no license is granted by default. Absent a license, copyright stays with the author and reuse needs permission.

仓库里没有 `LICENSE` 文件，因此默认不授予任何许可。缺少许可时版权仍归作者，复用需要获得同意。

If you want to reuse the text, open an issue on this repository first.

如果要复用这里的文字，请先在这个仓库开一个 issue 沟通。
