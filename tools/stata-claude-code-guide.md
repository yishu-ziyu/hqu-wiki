# Stata + Claude Code 实证研究指南

> 用 AI 辅助 Stata 实证分析：命令执行、do-file 编写、数据查询一条龙。

---

## 适用场景

- 写 do-file 时让 AI 帮你生成 / 调试 Stata 代码
- 直接执行 Stata 命令，不用在 GUI 和终端之间反复切换
- 快速查询 Stata 官方文档
- 处理 `.dta` 数据文件：导入、清洗、分析

---

## 环境要求

| 软件 | 版本 | 说明 |
|------|------|------|
| Stata | 17+ | 支持 StataMP / StataSE / StataIC |
| Claude Code | 最新版 | [安装指南](https://docs.claude.com/claude-code) |
| 操作系统 | macOS / Linux | Windows 暂未测试 |

---

## 安装步骤

### 第一步：添加插件市场

```bash
claude plugins marketplace add dylantmoore/stata-skill
```

这会从 GitHub 仓库 `dylantmoore/stata-skill` 拉取插件列表。

### 第二步：安装 Stata Bundle 插件

```bash
claude plugins install stata-bundle
```

### 第三步：验证安装

```bash
claude plugins list
```

应看到：

```
❯ stata-bundle@stata-skill
    Version: 1.0.0
    Scope: user
    Status: ✔ enabled
```

### 一键安装

```bash
claude plugins marketplace add dylantmoore/stata-skill && claude plugins install stata-bundle
```

---

## 安装后能做什么

1. **执行 Stata 命令** — 通过 MCP 接口直接运行 Stata 命令，结果实时返回
2. **Do-file 编辑** — 创建和编辑 Stata do-file 脚本，AI 辅助编写
3. **数据分析** — 导入、清洗、分析 Stata 数据文件（`.dta`）
4. **文档查询** — 快速查询 Stata 官方 PDF 文档中的命令用法

---

## 卸载

```bash
claude plugins uninstall stata-bundle
claude plugins marketplace remove stata-skill
```

---

## 常见问题

**Q: 提示 "Plugin not found" 怎么办？**
A: 确保第一步 marketplace 添加成功，再执行 install 命令。

**Q: 插件安装范围是什么？**
A: `user` 范围对该用户的所有项目全局可用，无需每个项目单独配置。

**Q: 需要每次都安装吗？**
A: 插件是用户级安装，一次安装后所有项目都可用，不需要重复配置。

---

## 相关资源

- 插件源码：[dylantmoore/stata-skill](https://github.com/dylantmoore/stata-skill)
- Stata 官方文档：[Stata Documentation](https://www.stata.com/documentation/)
