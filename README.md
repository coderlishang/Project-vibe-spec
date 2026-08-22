# Project Vibe Spec

用于 Vibe Coding 项目工作规范：在用户确认的需求与数据决策、代码、文档、测试、进度和 Git 交付之间保持同一份可追溯的事实来源。

它是一个通用 Agent Skill：基于跨工具的 `SKILL.md` 标准，可直接用于 Claude Code、Codex 以及其他支持该格式的编码 Agent。它不会替代仓库现有的 `AGENTS.md` / `CLAUDE.md`。已有项目规则优先；本 Skill 提供一套可复制的起步模板和一条稳定的执行闭环。

## 包含内容

- `SKILL.md`：首次接入、需求确认、跨模块影响分析、数据设计确认、计划、进度、文档联动、验证与交付规则。
- `assets/governance-starter/`：新项目可复制的项目契约、目录索引、需求、决策、Bug、PDD、PRD、UI、项目进度、功能进度和业务流程模板。
- `references/document-maintenance.md`：文档职责、更新矩阵、跨模块记录与行为验收规则。
- `references/decision-gates.md`：需求、数据表与 DDL 变更的方案确认清单。

## 安装

仓库同步托管在 GitHub 和 Gitee。安装目录名统一使用 `vibe-spec`，与 SKILL.md 中的 `name` 保持一致。

### Claude Code

个人级（所有项目可用）：

GitHub：

```bash
git clone https://github.com/coderlishang/Project-vibe-spec \
  ~/.claude/skills/vibe-spec
```

Gitee：

```bash
git clone https://gitee.com/codelishang/project-vibe-spec \
  ~/.claude/skills/vibe-spec
```

项目级（仅当前仓库可用，可随仓库分发给团队）：

GitHub：

```bash
git clone https://github.com/coderlishang/Project-vibe-spec \
  .claude/skills/vibe-spec
```

Gitee：

```bash
git clone https://gitee.com/codelishang/project-vibe-spec \
  .claude/skills/vibe-spec
```

安装后重启 Claude Code，在会话中通过 `/vibe-spec` 调用。

### Codex

GitHub：

```bash
git clone https://github.com/coderlishang/Project-vibe-spec \
  ~/.codex/skills/vibe-spec
```

Gitee：

```bash
git clone https://gitee.com/codelishang/project-vibe-spec \
  ~/.codex/skills/vibe-spec
```

重启或重新扫描 Codex 后，在会话中通过 `$vibe-spec` 调用。

### 其他 Agent

只要工具支持 `SKILL.md` 技能格式，把本仓库放入该工具的技能目录即可；`agents/openai.yaml` 是 Codex 的展示元数据，其他工具可忽略。

## 使用示例

Claude Code：

```text
使用 /vibe-spec，为这个仓库建立项目契约和需求台账。
```

Codex：

```text
使用 $vibe-spec，为这个仓库建立项目契约和需求台账。
```

```text
使用 vibe-spec 修复这个问题，并同步相关文档与验证结果。
```

## 边界

首次接入会先审视仓库已有文档；同类目录会被沿用，缺失职责才使用模板补齐。随后将真实位置写入目标仓库根目录的 `DOCUMENT_MAP.md`，并在 `AGENTS.md` 中关联这个索引。仓库需要 `CLAUDE.md` 时，其中只写一行指针 `@AGENTS.md`（Claude Code 的导入语法），规则仍只维护 `AGENTS.md` 一份。

模板提供默认结构。将技术栈、运行命令、远程仓库、部署方式、产品规则和具体业务流程写入目标项目自己的契约文档，不要写死在通用 Skill 中。
