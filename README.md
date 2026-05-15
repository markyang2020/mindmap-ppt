# Mindmap PPT Skill

用自然语言让 Agent 生成一个可以直接打开的思维导图 PPT 静态页面。

本仓库自带一个已经生成好的示例页面。下载源码后，直接双击打开：

```text
index.html
```

就可以预览效果。不需要执行 `npm run dev`，也不需要安装 npm 依赖。

## 1. 安装 Skill

### 安装到当前项目目录

```bash
npx skills add markyang2020/mindmap-ppt --skill mindmap-ppt-builder
```

这会把 skill 安装到你当前命令所在项目的目录里，通常会生成：

```text
./.agents/skills/mindmap-ppt-builder/
./skills-lock.json
```

只在这个项目里使用时，用这个命令。

### 安装到 Codex 全局目录

```bash
npx skills add markyang2020/mindmap-ppt --skill mindmap-ppt-builder --agent codex --global
```

这会把 skill 安装到 Codex 的用户级全局目录，通常是：

```text
~/.codex/skills/mindmap-ppt-builder/
```

以后在任意项目里都想使用时，用这个命令。

## 2. 让 Agent 生成页面

安装后，直接用自然语言和 Agent 说需求：

```text
使用 mindmap-ppt-builder，把这份产品方案生成一个思维导图 PPT 静态页面。
目标受众是老板，演示时间 5 分钟，风格简洁专业。
```

也可以给本地文件：

```text
使用 mindmap-ppt-builder，把 ./docs/方案.md 生成一个可播放的思维导图 PPT。
```

Agent 会生成或更新一个静态页面项目，主要文件是：

```text
index.html
src/main.js
src/styles.css
project/source.js
project/图片素材
```

## 3. 打开预览

直接双击生成目录里的：

```text
index.html
```

## AGENTS.md 是什么

`AGENTS.md` 是给 Agent 看的项目规则文件，不是给普通用户操作的文档。

它告诉 Agent：

- 导图内容应该写到 `project/source.js`
- 图片素材应该放到 `project/`
- 节点文本、图片引用、布局和交互要遵守什么规则
- 这个项目是纯 HTML + JS + CSS，不需要启动开发服务

普通用户只需要看 README 和打开 `index.html`。

## 部署

把生成目录整体上传到 Nginx、对象存储、GitHub Pages、Netlify 或任意静态服务器即可。
