# commit

> Version: v1.1.0

将用户级 `/commit` 命令抽象为可复用 skill。

## 内容

- `SKILL.md`：提交流程与约束
- `resources/source-command.md`：原始命令来源文本
- `agents/openai.yaml`：UI 元信息

## 使用

- 当用户要求“提交当前改动”时触发。
- 目标是一次性完成审查 + 暂存 + 提交。
- 默认采用引导式数字选项交互（如 `1/2/3`），用户只需选择即可继续。
- 提交后支持继续引导：`1. 推送远程` / `2. 仅本地提交`。
