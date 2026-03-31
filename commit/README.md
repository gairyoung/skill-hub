# commit

> Version: v1.2.0

将用户级 `/commit` 命令抽象为可复用 skill。

## 内容

- `SKILL.md`：提交流程与约束
- `resources/source-command.md`：原始命令来源文本
- `agents/openai.yaml`：UI 元信息

## 使用

- 当用户要求“提交当前改动”时触发。
- 目标是一次性完成审查 + 暂存 + 提交。
- 默认采用单次引导式数字选项交互（`1-6`），用户只需选择即可继续。
- 提交信息由技能自动生成（Conventional Commits），不再单独确认提交文案。
- `git push` 与提交流程合并为同一次选择（如“提交本次任务相关修改并推送到远程”）。
