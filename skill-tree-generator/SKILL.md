---
name: skill-tree-generator
description: "将当前所有已安装的 Skill 以工作树形式输出到用户指定位置或默认桌面文件，并展示给用户。触发条件：用户要求查看 skill 工作树、skill 列表、所有 skill、skill 总览。"
---

# Skill Tree Generator

将当前OpenClaw已安装的所有Skill以工作树形式输出。

## 工作路径
- Skill 目录：默认使用 `$HOME/.openclaw/workspace/skills`，也可按用户实际配置调整。
- 输出文件：优先使用用户指定位置；未指定时使用 `$HOME/Desktop/Skill工作树.md`。

## 操作步骤

1. 读取用户实际配置的 OpenClaw Skills 目录；未特别配置时读取 `$HOME/.openclaw/workspace/skills` 下所有目录
2. 读取每个skill的 `SKILL.md` 中的 `description` 字段
3. 按类别分组整理
4. 生成Markdown格式的工作树
5. 写入目标文件
6. 将内容展示给用户

## 输出格式

```
## 📦 Skill总览（共XX个）

### 🎯 默认加载（Always On）
| Skill | 作用 |
|-------|------|
| xxx | xxx |

### 🌐 联网 & 搜索
...

### 📄 文档处理（四件套）
...

[以此类推]
```

## 分类标准

- **默认加载**：metadata.openclaw.always: true
- **联网&搜索**：web/search/crawl相关
- **文档处理**：docx/xlsx/pdf/pptx
- **记忆&学习**：memory/notes/learning相关
- **研究&调研**：research/market/quant相关
- **编程&开发**：coding/develop相关
- **Agent增强**：agent/meta相关
- **系统&工具**：system/tools相关
