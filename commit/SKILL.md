---
name: commit
description: Use when creating a single git commit from current workspace changes, with fast review, staging, and one-shot commit execution.
---

# Commit Skill

## 版本

- 当前版本：`v1.0.0`

## 概述

该技能用于快速完成一次标准 Git 提交：检查变更、审查风险、暂存文件、生成提交信息并执行提交。

## 适用场景

1. 用户明确要求“提交当前改动”。
2. 目标是一次性提交当前工作区变更。
3. 需要统一采用 Conventional Commits 风格。

## 执行步骤

1. 检查当前状态：
   - `git status`
   - `git diff --staged`
   - `git diff`
2. 快速审查：
   - 是否有明显逻辑错误、安全风险、无关改动。
3. 暂存文件：
   - 默认 `git add -A`，或按用户要求选择性暂存。
4. 生成提交信息：
   - 使用 `<type>(<scope>): <description>`。
5. 执行提交：
   - `git commit -m "..."`。
6. 推送策略：
   - 仅在用户明确要求时执行 `git push`。

## 约束

1. 提交前必须基于真实 diff，而非猜测。
2. 不要把无关文件混入同一次提交。
3. 若存在阻断问题，先反馈问题再提交。

## 参考资源

- `resources/source-command.md`：原始 `/commit` 命令定义。
