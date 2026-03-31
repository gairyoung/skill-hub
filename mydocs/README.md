# MyDocs Skill

> Version: v1.0.0
> Maintainer: FlyBird

`mydocs` 是用于 `docs/` 文档体系的 AI-first 规范技能，目标是让 Claude/Codex 对文档做到高保真理解与执行，同时保持开发者可读性。

## 能力概览

- 统一文档命名（`arch-spec`）与章节结构
- 支持 `add / update / review` 三种模式
- 默认自动执行，风险动作触发确认闸门
- 维护 `docs/plans/` 之外的“最新单一版本”
- 基于关键变更更新 `DOC_VERSION_LOG.md`

## 模式说明

- `add`：新增功能域文档与初始化结构
- `update`：更新现有文档（默认）
- `review`：文档评审（默认不改文件）

## 关键约束

1. 执行前必须读取：
   - `docs/README.md`
   - `docs/DOCUMENTATION_STANDARDS.md`
   - `docs/DOC_VERSION_LOG.md`
2. 除 `docs/plans/` 外，文档保持最新单一版本。
3. 仅关键性变更写入版本日志（避免过密记录）。

## 目录结构

```text
mydocs/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── resources/
    ├── README.md
    ├── DOCUMENTATION_STANDARDS.md
    └── DOC_VERSION_LOG.md
```

## 使用示例

- `/mydocs add syncer`
- `/mydocs update syncer`
- `/mydocs review syncer`

## 发布建议

发布前执行：

```bash
python3 /Users/GairYang/.codex/skills/.system/skill-creator/scripts/quick_validate.py .claude/skills/mydocs
```

若有规范变更，更新：

- `SKILL.md` 版本号
- `README.md` 版本号
- `agents/openai.yaml`（必要时）
