# 文档结构与编写规范

> 生成时间：YYYY-MM-DD HH:mm:ss
> 版本：v1.0

## 1. 目标

定义 `docs/` 的统一结构、命名规则和更新流程，确保文档可维护、可追溯、可执行。
文档主要用于让 AI（Claude Code、Codex）准确理解并高保真执行，同时兼顾开发人员阅读。

## 2. 目录结构基线

```text
docs/
├── README.md
├── DOCUMENTATION_STANDARDS.md
├── DOC_VERSION_LOG.md
├── _templates/
│   └── arch-spec-template.md
├── plans/
├── tech/
└── {feature-domain}/
    ├── PRD.md
    ├── arch-spec.md
    ├── DEV_TECH.md
    ├── DEV_PLAN.md
    └── CHANGELOG.md
```

## 3. 命名规范

### 3.1 长期维护文档

- 功能域目录下固定命名：`PRD.md`、`arch-spec.md`、`DEV_TECH.md`、`DEV_PLAN.md`、`CHANGELOG.md`。

### 3.2 一次性阶段文档

- 使用格式：`YYYY-MM-DD-{topic}-{doc-type}.md`
- `doc-type` 建议值：`prd`、`arch-spec`、`implementation-plan`、`acceptance-report`、`postmortem`

## 4. arch-spec 章节顺序（强制）

1. 背景、目标、范围、非目标
2. 整体架构与不变量
3. 核心流程与异常恢复
4. 数据模型与迁移
5. API 与事件契约
6. 组件与模块边界
7. UI/UX/UE 与信息架构
8. 可观测性与验收标准
9. 发布、回滚与分期计划
10. 风险与开放问题

## 5. 元信息规范

所有新增或重大更新文档必须包含：

- 生成时间：`YYYY-MM-DD HH:mm:ss`
- 版本：`vX.Y`

## 6. AI 可执行性规范（强制）

文档必须明确：

1. 输入与前置条件
2. 输出与验收标准
3. 约束与不变量
4. 主流程与异常恢复
5. 数据与接口契约

禁止使用无法执行的模糊表达（如“适当”“尽量”）而不提供默认值。

## 7. SSOT 与最新性规则

1. 同主题优先更新旧文档，不新建重复文档。
2. 新需求与旧文档冲突时，先更新文档，再改代码。
3. 实现完成后，文档必须在同一变更中同步更新。
4. 除 `docs/plans/` 外，其余文档必须保持“最新单一版本”。
5. 关键性变更时更新 `docs/DOC_VERSION_LOG.md`，不要求密集记录。
6. 被替代文档在版本日志中标记为 `superseded` 并指向替代文件。

关键性变更包括：

- 新增/废弃文档
- 架构、流程、数据模型、API 契约变化
- 验收标准、SLO、发布/回滚策略变化
- 文档主/次版本升级

## 8. 评审清单

1. 是否写清范围与非目标。
2. 是否定义不变量、失败恢复和回滚策略。
3. 是否覆盖数据迁移和兼容策略。
4. 是否包含可观测性（日志、指标、告警）。
5. 是否给出可验证验收标准。
6. 是否满足 AI 可执行性规范。
7. 版本日志是否同步更新，且除 `docs/plans/` 外不存在过期并存文档。

## 9. 变更记录

| 日期 | 版本 | 说明 |
|------|------|------|
| YYYY-MM-DD | v1.0 | 初始模板 |
