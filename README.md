# novel-creation

Spec Kit 风格的规格驱动长篇小说创作工作流，打包为 [Google Antigravity CLI](https://antigravity.google/docs/cli/plugins/) 插件（单目标，iFlow 格式已移除）。

## 安装

```bash
agy plugin install ./antigravity-plugin
agy plugin list        # 确认 novel-creation 已启用
```

卸载：`agy plugin uninstall novel-creation`。

## 工作流命令

| 命令 | 作用 |
|------|------|
| `/speckit-constitution` | 创建或更新项目宪章（创作原则），并同步依赖模板 |
| `/speckit-specify` | 从一句自然语言描述生成书籍/功能规格（spec.md） |
| `/speckit-clarify` | 对规格中的模糊点提出最多 5 个澄清问题并回写 |
| `/speckit-plan` | 生成设计文档（research、data-model、quickstart 等） |
| `/speckit-tasks` | 生成按依赖排序的可执行任务清单（tasks.md） |
| `/speckit-implement` | 按 tasks.md 逐项执行落地 |
| `/speckit-analyze` | 跨 spec/plan/tasks 做一致性审查 |
| `/speckit-checklist` | 按当前阶段生成自定义检查清单 |

典型顺序：constitution → specify → clarify → plan → tasks → implement，analyze / checklist 按需穿插。

## 项目脚手架

技能正文会调用工作目录下的 `.specify/`（脚本、模板、宪章记忆）。开一本新书：

```bash
cp -r .specify /path/to/your-novel-repo/   # 或直接在本仓库下为每本书开分支
```

所有命令请在该书稿仓库根目录下运行。

## 上下文文件

Antigravity CLI 读取项目根目录的 `AGENTS.md`（或 `GEMINI.md`）。执行 `/speckit-plan` 后，可运行以下脚本把项目约定写回上下文：

```bash
.specify/scripts/bash/update-agent-context.sh antigravity
```

## 目录结构

```
antigravity-plugin/
├── plugin.json                      # 插件清单（name: novel-creation）
└── skills/
    └── speckit-<name>/SKILL.md      # 8 个技能，自动注册为斜杠命令
.specify/
├── memory/constitution.md           # 宪章
├── scripts/bash/                    # 工作流脚本
└── templates/                       # spec/plan/tasks 等模板
```
