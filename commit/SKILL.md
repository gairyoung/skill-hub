---
name: commit
description: Use when creating a single git commit from current workspace changes and the flow should continue via guided option selection instead of manual text input.
---

# Commit Skill

## 版本

- 当前版本：`v1.1.0`

## 概述

该技能用于快速完成一次标准 Git 提交：检查变更、审查风险、暂存文件、生成提交信息并执行提交。默认采用引导式选项交互（数字选择）推进流程。

## 交互原则（引导式）

1. 仅使用“选项式提问”，不要求用户手动输入完整命令或自由文本。
2. 每一步给出明确序号（如 `1` / `2` / `3`），用户回复序号即可继续。
3. 每次提问都应包含“推荐项”，并支持默认继续（未明确说明时按推荐项）。
4. 提交信息默认给出 2-3 个候选，用户选择序号即可，不强制自定义。

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
3. 提交范围选择（引导式）：
   - `1. 全部暂存（推荐）`
   - `2. 选择性暂存（按文件分组给出编号）`
   - `3. 取消本次提交`
4. 暂存文件：
   - 选择 `1` 时执行 `git add -A`；
   - 选择 `2` 时按编号暂存对应文件。
5. 生成提交信息候选（Conventional Commits）：
   - 例如提供 `1/2/3` 三条候选，用户选序号。
6. 执行提交：
   - `git commit -m "..."`。
7. 推送确认（引导式）：
   - 提交后询问：`1. 推送到远程（推荐）` / `2. 仅本地提交`。
   - 仅在用户选择 `1` 时执行 `git push`。

## 约束

1. 提交前必须基于真实 diff，而非猜测。
2. 不要把无关文件混入同一次提交。
3. 若存在阻断问题，先反馈问题再提交。
4. 所有交互优先采用数字选项，不要求用户手写复杂输入。

## 参考资源

- `resources/source-command.md`：原始 `/commit` 命令定义。
