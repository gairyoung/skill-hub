# skill-hub

个人 Skills 仓库，用于集中维护可复用的 AI Skill（主要面向 Claude Code / Codex）。

## 目录

- [`mydocs/`](./mydocs) - 文档体系规范 Skill（支持 `add / update / review`）
- [`commit/`](./commit) - Git 提交 Skill（快速审查 + 一次性提交）

## 推荐技能模块（纯文档）

### 推荐 01：gstack 角色化技能组

参考仓库：[gstack](https://github.com/garrytan/gstack)

核心思路：这不是若干“提示词”，而是把一个人拆分成一支协作团队。

- `/ceo-review`：以 CEO 视角审查产品决策
- `/eng-manager`：以工程经理视角做代码审查和架构决策
- `/designer`：以产品设计师视角评估用户体验
- `/qa`：以 QA 工程师视角做测试和质量把关
- `/release-manager`：管理发布流程
- `/doc-engineer`：撰写技术文档
- `/plan`：制定开发计划

推荐用法：先 `plan`，再按角色并行评审，最后 `release-manager` 收敛发布。

### 推荐 02：web-access 联网技能组

参考仓库：[web-access](https://github.com/eze-is/web-access)

核心思路：补齐 Agent 的完整联网执行能力，不只“搜到信息”，还要“拿到页面真实结果”。

- 联网策略自动选择：WebSearch / WebFetch / curl / Jina / CDP 按场景组合
- 浏览器自动化：通过 CDP 复用本机 Chrome 登录态，支持动态页面交互
- 并行执行与站点经验沉淀：多目标分治，按域名复用已验证的操作路径

推荐用法：先用常规检索定位信息，再在关键页面切换 CDP 模式做高保真验证与执行。

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
