# Claude Code Skill 系统详解

## 什么是 Skill

Skill 是 Claude Code 的能力扩展包，定义了特定场景下的行为模式、知识库和工作流程。

## Skill 结构

```
my-skill.skill/
├── SKILL.md        # 核心定义（必需）
├── assets/         # 图片、数据等资源
├── templates/      # 输出模板
└── examples/       # 使用示例
```

### SKILL.md 格式

```yaml
---
name: my-skill
description: 技能描述
version: 1.0.0
model: claude-4
---

# 角色定位

你是一位...

## 触发条件

当用户问到...时激活

## 工作流程

1. 第一步...
2. 第二步...
```

## 创建自定义 Skill

```bash
# 交互式创建
claude skill create

# 指定名称创建
claude skill create coding-assistant
```

## 常用 Skill 类型

| 类型 | 用途 | 示例 |
|------|------|------|
| 语言专家 | 编程语言指导 | python-expert |
| 框架专家 | 框架使用指导 | react-expert |
| 调试专家 | Bug 定位与修复 | debug-master |
| 架构师 | 系统设计 | solution-architect |
| 审阅者 | 代码审查 | code-reviewer |

## 加载与切换

```bash
# 加载
claude skill load react-expert

# 查看当前 Skill
claude skill current

# 卸载
claude skill unload

# 列出所有 Skill
claude skill list
```

## 最佳实践

1. **单一职责**：每个 Skill 只做一件事
2. **明确触发**：清晰定义激活条件
3. **模板化输出**：统一输出格式
4. **版本管理**：记录变更历史

---

> 版本：1.0