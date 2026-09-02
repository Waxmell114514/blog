# 个人主页 / Blog

Ziwei Liu 的个人主页与博客，基于 [Academic Pages](https://github.com/academicpages/academicpages.github.io)
（Jekyll + Minimal Mistakes）模板，由 GitHub Pages 托管。

线上地址：<https://waxmell114514.github.io/blog/>

## 目录结构

| 路径 | 作用 |
| --- | --- |
| `_config.yml` | 站点全局配置：标题、`url` / `baseurl`、侧边栏个人信息、社交链接 |
| `_data/navigation.yml` | 顶部导航栏的条目与顺序 |
| `_pages/about.md` | 首页（`/`） |
| `_pages/cv.md` | CV 页面（`/cv/`） |
| `_pages/research.html` | Research 列表页（`/research/`） |
| `_research/*.md` | 每个研究项目一个文件，会出现在 `/research/` 和 CV 页面 |
| `_posts/*.md` | 博客文章，文件名必须是 `YYYY-MM-DD-标题.md` |
| `files/` | 可下载的附件，例如 `files/Ziwei_Liu_CV.pdf` |
| `images/` | 图片，其中 `images/profile.png` 是侧边栏头像 |

## 常见操作

### 写一篇新博客

在 `_posts/` 下新建 `2026-09-15-my-post.md`：

```markdown
---
title: "文章标题"
date: 2026-09-15
permalink: /posts/2026/09/my-post/
tags:
  - mechanistic interpretability
excerpt: "列表页显示的一句话摘要。"
---

正文（Markdown）。支持 MathJax 公式和 Mermaid 图。
```

### 新增一个研究项目

在 `_research/` 下新建一个 `.md` 文件，front matter 里写 `collection: research`、
`title`、`excerpt` 和 `date`（列表按日期倒序排列）。

### 更新 CV

CV 页面的正文直接写在 `_pages/cv.md` 里。换 PDF 时把新文件放到
`files/Ziwei_Liu_CV.pdf`（保持文件名不变，否则要同步改 `_pages/cv.md` 和
`_pages/about.md` 里的链接）。

### 换头像

替换 `images/profile.png`（目前还是模板自带的占位图）。

### 换配色

`_config.yml` 里的 `site_theme` 可选 `default`、`air`、`sunrise`、`mint`、`dirt`、
`contrast`。

## 本地预览

```bash
bundle install
bundle exec jekyll serve -l -H localhost
# 打开 http://localhost:4000/blog/
```

也可以用 Docker：`docker compose up`。

## 部署

仓库设置 → Pages → Source 选 **Deploy from a branch**，分支选 `master`、目录选
`/ (root)`。GitHub Pages 会自动用 Jekyll 构建。

因为仓库名是 `blog` 而不是 `waxmell114514.github.io`，站点位于子路径下，所以
`_config.yml` 里必须保持 `baseurl: "/blog"`。如果以后把仓库改名成
`waxmell114514.github.io`，记得把 `baseurl` 改回空字符串。

页面里的内部链接请统一写成 `{% raw %}{{ base_path }}/xxx/{% endraw %}`（页面顶部需要有
`{% raw %}{% include base_path %}{% endraw %}`），不要写死 `/xxx/`，否则子路径下会 404。

## 模板里被移除的部分

为了让站点保持干净，模板自带的 Publications / Talks / Teaching / Portfolio 示例页面和
示例内容都已删除。这几个 collection 仍然保留在 `_config.yml` 里，将来需要时可以从
[上游仓库](https://github.com/academicpages/academicpages.github.io/tree/master/_pages)
把对应的 `_pages/publications.html`、`_pages/talks.html`、`_pages/teaching.html`
拿回来，再在 `_data/navigation.yml` 里加上导航条目。

## License

模板部分沿用上游的 MIT License，见 [LICENSE](LICENSE)。
