# CLAUDE.md

本文件为 Claude Code（claude.ai/code）在本仓库中进行开发时提供指引。

## 项目概述

这是一个基于浏览器的 HTML5 小游戏合集。每个游戏都是一个独立的单 HTML 文件，内嵌 CSS 和 JavaScript —— 无需构建步骤、无外部依赖、无包管理器。

## 运行游戏

直接用浏览器打开任意 `.html` 文件即可：

```bash
open tetris.html   # macOS
open snake.html
```

或通过本地 HTTP 服务器运行：

```bash
python3 -m http.server 8080
# 然后访问 http://localhost:8080/tetris.html
```

## 文件结构

| 文件 | 说明 |
|------|------|
| `tetris.html` | 俄罗斯方块 —— 深色主题，基于 Canvas |
| `snake.html` | 贪食蛇 —— 粉嫩色主题，可爱的红色小蛇吃香蕉，基于 Canvas |

## 开发规范

新增游戏时请遵循以下现有模式：

- **单文件**：每个游戏是一个独立的 `.html` 文件，内联 `<style>` 和 `<script>`。
- **Canvas 渲染**：游戏通过 HTML5 Canvas 绘制，使用 `requestAnimationFrame` 作为游戏循环。
- **中文界面**：游戏标题、标签和操作说明使用简体中文（`zh-CN`）。
- **响应式**：在适当时加入 `@media` 媒体查询以适配移动端。
- **按钮控制**：除键盘控制外，提供屏幕上的控制按钮（开始、重新开始、暂停）。
- **状态管理**：使用标志位跟踪游戏状态，如 `isGameStarted`、`isPaused`、`isGameOver`。
- **本地存储**：谨慎使用 `localStorage`（如 `snake.html` 中的最高分记录）。

## 代码风格

- 使用原生 JavaScript（不使用框架）。
- 使用 `const` / `let`；避免使用 `var`。
- 优先使用 `addEventListener`，避免内联事件处理器。
- 绘制函数应只负责纯渲染 —— 更新逻辑应放在游戏循环中。


## 回馈
每次任务执行完毕后，请回复我（输出）：主人，任务已完成！