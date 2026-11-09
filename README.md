# lany-styleguide-skills

面向 AI 编程助手的 Google 风格指南技能集合。每个技能都包含
`SKILL.md` 使用说明和 `references/deep.md` 详细规范。

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

## 安装到 Codex

将需要的技能目录复制到 `$CODEX_HOME/skills`。未设置 `CODEX_HOME` 时，默认
目录为 `~/.codex/skills`。例如，在仓库根目录运行：

```bash
cp -R google-style-python google-style-ts ~/.codex/skills/
```

将示例中的目录名替换为需要安装的技能。安装后，Codex 会在相关语言或
文档任务中调用对应技能；也可以直接阅读技能目录中的 `SKILL.md` 和
`references/deep.md`。

## 来源

本仓库的技能内容整理自
[byoungfeng/styleguide-skills](https://github.com/byoungfeng/styleguide-skills)。
