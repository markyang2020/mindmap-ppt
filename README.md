# Mindmap PPT Skill

用自然语言让 Agent 生成一个可以直接打开的思维导图 PPT 静态页面。

## 1. 安装 Skill

安装到当前环境：

```bash
npx skills add markyang2020/mindmap-ppt --skill mindmap-ppt-builder
```

安装到 Codex 全局：

```bash
npx skills add markyang2020/mindmap-ppt --skill mindmap-ppt-builder --agent codex --global
```

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

不需要执行 `npm run dev`，不需要安装 npm 依赖。

## 部署

把生成目录整体上传到 Nginx、对象存储、GitHub Pages、Netlify 或任意静态服务器即可。
