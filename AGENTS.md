# PROJECT KNOWLEDGE BASE

**Generated:** 2026-04-01
**Commit:** 935a30a
**Branch:** main

## OVERVIEW

Personal GitHub Pages 静态站点 (www.986771093.xyz)。纯 HTML — 无构建工具、无框架、无包管理器。每个页面自包含（inline CSS + JS）。

## STRUCTURE

```
./
├── index.html           # 主页：2025 前端新特性展示（霓虹街景风格）
├── demos/
│   ├── jenga.html       # Three.js 物理破坏模拟游戏
│   └── texas.html       # 德州扑克记账台（移动端优先）
├── tools/
│   └── calculate.html   # 四则运算练习（适老化大字体）
├── boolv/dev/
│   ├── parse_log.html   # BoolVideo 日志解析器（Markdown 渲染）
│   └── detect_music.html # 音频节拍/片段可视化
├── CNAME                # GitHub Pages 自定义域名
└── .gitignore           # 仅忽略 .DS_Store
```

## WHERE TO LOOK

| Task | Location | Notes |
|------|----------|-------|
| 新增独立页面 | 按功能放入 `demos/`、`tools/` 或 `boolv/dev/` | 每页自包含，不依赖共享资源 |
| 修改主页 | `index.html` | CSS 变量在 `:root`，scroll-driven animations |
| 域名配置 | `CNAME` | 当前指向 www.986771093.xyz |
| 工作相关工具 | `boolv/dev/` | BoolVideo 内部开发工具 |

## CONVENTIONS

- **零构建流程**：直接编辑 HTML 文件，push 即部署
- **自包含页面**：每个 HTML 文件包含所有 CSS 和 JS，无共享样式表或脚本
- **外部依赖通过 CDN**：Three.js (importmap)、marked.js、highlight.js、pretty-json — 不本地安装
- **中文优先**：`lang="zh-CN"` 为默认，界面文案用中文
- **CSS 变量**：每页在 `:root` 定义自己的配色方案
- **移动端适配**：部分页面设置 `user-scalable=no` + `touch-action: manipulation`
- **暗色主题居多**：index、demos、boolv 均使用深色背景

## ANTI-PATTERNS

- 无 — 代码中未发现 TODO/FIXME/HACK 等标记

## COMMANDS

```bash
# 本地预览（任意静态服务器）
python3 -m http.server 8080
# 或
npx serve .

# 部署
git push origin main  # GitHub Pages 自动部署
```

## NOTES

- `index.html` 使用 CSS `scroll-driven animations`、`anchor positioning`、`@starting-style` 等 2025 新特性 — 需要最新版 Chrome
- `boolv/` 是工作（BoolVideo）相关的内部工具，与个人项目分开
- 无 CI/CD、无 lint、无测试 — 纯手工静态站点
- `README.md` 仅占位，无实际内容
