# Claude Code 配置仓库

个人 Claude Code 配置：CLAUDE.md、规则（rules）、技能（skills）。

## 使用方式

### 首次部署（克隆到 `~/.claude/`）

```bash
# 备份现有配置
cp -r ~/.claude ~/.claude.bak

# 克隆仓库
git clone https://github.com/Myoiyu/Cluade-setting.git ~/.claude
```

### 更新配置

```bash
cd ~/.claude
git pull origin main
```

### 修改配置后上传

```bash
cd ~/.claude
git add -A
git commit -m "更新规则/技能"
git push origin main
```

## 目录结构

```
~/.claude/
├── CLAUDE.md          # 规则入口，索引 rules/ 下的各规则文件
├── rules/             # 模块化规则文件
│   ├── coding.md      # 编码规则
│   ├── language.md    # 语言规范（简体中文）
│   ├── code-change-command.md  # 代码修改注释规范
│   ├── session-memory.md       # 跨会话记忆规则
│   ├── large-log-analysis.md   # 大日志分析规则
│   ├── question-ask.md         # Android 调试规则
│   ├── report-style.md         # 报告与文档输出规则
│   └── dingtalk.md             # 钉钉通知规则
└── skills/            # 自定义技能
    ├── git-push/      # 自动 git commit & push
    ├── str-debug/     # Android STR 待机日志分析
    └── jira-analyze/  # Jira 问题单分析与解决
```

## 注意事项

- `session_memory.md`、`settings.json`、`history.jsonl` 等本地文件已在 `.gitignore` 中排除，不会上传。
- 在新机器上部署后，需要按实际环境调整 `settings.json`。
