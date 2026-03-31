# skill-hub

个人 Skills 仓库，用于集中维护可复用的 AI Skill（主要面向 Claude Code / Codex）。

## 目录

- [`mydocs/`](./mydocs) - 文档体系规范 Skill（支持 `add / update / review`）
- [`commit/`](./commit) - Git 提交 Skill（快速审查 + 一次性提交）

## 使用方式

### 1) 克隆仓库

```bash
git clone https://github.com/gairyoung/skill-hub.git
```

### 2) 安装单个 Skill（示例：mydocs / commit）

将目标 skill 目录复制到你的 skills 目录：

- Claude Code 常见路径：`~/.claude/skills/`
- Codex 常见路径：`~/.codex/skills/` 或 `$CODEX_HOME/skills/`

例如：

```bash
cp -R skill-hub/mydocs ~/.claude/skills/
cp -R skill-hub/commit ~/.claude/skills/
```

## 版本维护

每个 Skill 自带：

- `SKILL.md`（规范与流程）
- `README.md`（说明）
- `agents/openai.yaml`（UI 元信息）
- `resources/`（模板与参考资源）
