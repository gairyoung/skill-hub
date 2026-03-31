# Docs 索引

> 生成时间：YYYY-MM-DD HH:mm:ss
> 版本：v1.0

## 1. 说明

本目录用于维护项目的需求、架构、技术方案与实施计划。
文档以 `docs/DOCUMENTATION_STANDARDS.md` 作为规范来源。
文档同时服务开发人员与 AI（Claude Code、Codex）；其中优先保证 AI 能高保真执行。

## 2. 目录索引（示例）

- `DOCUMENTATION_STANDARDS.md`：文档结构与命名规范（最高优先级）
- `DOC_VERSION_LOG.md`：文档版本状态日志（latest/superseded/draft）
- `_templates/arch-spec-template.md`：架构文档模板
- `plans/`：阶段计划、实施排期
- `tech/`：跨模块技术专题与优化记录
- `{feature-domain}/`：功能域文档（PRD、arch-spec、DEV_TECH、DEV_PLAN、CHANGELOG）

## 3. 新功能文档要求

新增功能时，至少维护以下文件：

- `docs/{feature-domain}/PRD.md`
- `docs/{feature-domain}/arch-spec.md`
- `docs/{feature-domain}/DEV_TECH.md`
- `docs/{feature-domain}/DEV_PLAN.md`
- `docs/{feature-domain}/CHANGELOG.md`

## 4. 更新约束

1. 同主题优先更新已有文档，不创建重复文档。
2. 文档与实现冲突时，先更新文档定义，再改代码。
3. 功能上线或重大变更后，必须同步更新相关文档。
4. 所有新增或大改文档必须包含“生成时间 + 版本”。
5. 除 `docs/plans/` 外，文档应保持最新单一版本，旧文档在版本日志中标记为 `superseded`。

## 5. 变更记录

| 日期 | 版本 | 说明 |
|------|------|------|
| YYYY-MM-DD | v1.0 | 初始模板 |
