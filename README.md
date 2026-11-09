# lany-styleguide-skills

为 AI 编程助手提供的 Google 风格指南技能集合。每个技能包含
`SKILL.md` 使用说明和 `references/deep.md` 详细规范，适用于支持
Agent Skills 格式的工具。

## 技能列表

| 技能 | 语言或格式 |
| --- | --- |
| `google-style-angularjs` | AngularJS |
| `google-style-cpp` | C++ |
| `google-style-csharp` | C# |
| `google-style-go` | Go |
| `google-style-htmlcss` | HTML、CSS |
| `google-style-java` | Java |
| `google-style-js` | JavaScript |
| `google-style-json` | JSON |
| `google-style-lisp` | Common Lisp |
| `google-style-markdown` | Markdown |
| `google-style-objc` | Objective-C、Objective-C++ |
| `google-style-python` | Python |
| `google-style-r` | R |
| `google-style-shell` | Shell |
| `google-style-ts` | TypeScript |
| `google-style-vim` | Vimscript |
| `google-style-xml` | XML |

## 平台兼容性

技能采用 `SKILL.md` + YAML frontmatter + Markdown 指令，并通过
`references/deep.md` 提供详细规则。以下工具支持或可导入这种目录结构：

| 工具 | 用户级目录 | 项目级目录 |
| --- | --- | --- |
| Codex | `~/.agents/skills/` | `.agents/skills/` |
| Claude Code | `~/.claude/skills/` | `.claude/skills/` |
| Grok | `~/.grok/skills/` | `.grok/skills/` |
| Kiro | `~/.kiro/skills/` | `.kiro/skills/` |
| Qoder CLI | `~/.qoder/skills/` | `.qoder/skills/` |
| QoderWork | `~/.qoderwork/skills/` | 通过应用导入 |
| WorkBuddy | 通过应用导入 | `.codebuddy/skills/` |

用户级路径适用于该账号下的所有项目；项目级路径只对当前仓库生效。
QoderWork 和 WorkBuddy 也可以从技能页面上传技能包。

## 安装

把需要的技能文件夹复制到对应工具的技能目录，保留整个文件夹，不能只复制
`SKILL.md`，因为技能会引用 `references/deep.md`。

例如，在 macOS 或 Linux 项目根目录安装 Python 和 TypeScript 技能：

```bash
mkdir -p .agents/skills
cp -R google-style-python google-style-ts .agents/skills/
```

将 `.agents/skills/` 替换成上表中对应的项目级目录，即可用于其他支持该
格式的工具。若使用用户级安装，请将目标换成对应的用户级目录。

### 各工具导入方式

- **Codex**：复制到 `.agents/skills/`（项目级）或
  `~/.agents/skills/`（用户级），然后重新开始会话。
- **Claude Code**：复制到 `.claude/skills/` 或 `~/.claude/skills/`。
  请求相关语言任务时自动触发，也可明确要求使用技能名。
- **Grok**：复制到 `.grok/skills/` 或 `~/.grok/skills/`。Grok CLI 可用
  `/skills` 查看、用 `/skills <技能名>` 加载技能。
- **Kiro**：复制到 `.kiro/skills/` 或 `~/.kiro/skills/`，也可在
  Agent Steering & Skills 面板选择导入 GitHub 技能目录。
- **Qoder CLI**：复制到 `.qoder/skills/` 或 `~/.qoder/skills/`，然后
  自动触发或通过 `/技能名` 调用。
- **QoderWork**：在 Skills 页面上传包含技能目录的 ZIP，或把技能目录复制到
  `~/.qoderwork/skills/`。
- **WorkBuddy**：桌面版可放入项目的 `.codebuddy/skills/`，也可在
 「专家·技能·连接器」页面上传技能包。上传时选择单个技能目录并保留
  `SKILL.md` 和 `references/`。

## 在项目中调用技能

先打开或切换到目标项目，再在对话中调用与文件语言匹配的技能。下面以
`google-style-python` 为例，要求助手检查项目中的 Python 文件并按规范修改：

```text
请使用 google-style-python 技能检查当前项目的 src/ 目录，找出不符合
Google Python 风格的代码并直接修复。完成后列出修改文件和主要调整。
```

支持快捷调用语法的平台可直接使用技能名：

| 工具 | 示例调用 |
| --- | --- |
| Codex | `$google-style-python 检查并修复当前项目的 src/` |
| Claude Code | `/google-style-python 检查并修复当前项目的 src/` |
| Grok | `/google-style-python 检查并修复当前项目的 src/` |
| Kiro | `/google-style-python 检查并修复当前项目的 src/` |
| Qoder CLI | `/google-style-python 检查并修复当前项目的 src/` |
| QoderWork | 在 Skills 页面启用技能，再要求检查当前项目的 `src/` 目录 |
| WorkBuddy | 在对话中添加该技能，再要求检查当前项目的 `src/` 目录 |

把 `google-style-python` 换成其他技能名，并将 `src/` 换成项目中的目标目录。
也可以要求助手先审查并报告问题，不直接修改文件。

## 来源

本仓库的技能内容整理自
[byoungfeng/styleguide-skills](https://github.com/byoungfeng/styleguide-skills)。

## 参考文档

- [Codex Skills](https://developers.openai.com/codex/skills)
- [Claude Code Skills](https://docs.anthropic.com/en/docs/claude-code/skills)
- [Grok Skills](https://github.com/xai-org/grok-build/blob/main/crates/codegen/xai-grok-shell/README.md)
- [Kiro Agent Skills](https://kiro.dev/docs/cli/skills/)
- [Qoder Skills](https://docs.qoder.com/cli/Skills)
- [WorkBuddy Skills](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market)
