# 个人博客

这是一个基于 [saicaca/fuwari](https://github.com/saicaca/fuwari) 改造的个人博客。底层使用 Astro，构建产物是纯静态文件，适合部署到国内对象存储、CDN 或自己的服务器。

## 功能

- Astro + Tailwind CSS
- Markdown 写作
- 标签、分类、归档
- RSS
- 本地搜索 Pagefind
- 亮色/暗色模式
- 无运行时后端依赖

## 开发

```sh
pnpm install
pnpm dev
```

新建文章：

```sh
pnpm new-post my-post
```

文章位置：`src/content/posts/`

站点配置：`src/config.ts`

关于页面：`src/content/spec/about.md`

## 构建

```sh
pnpm build
pnpm preview
```

正式域名通过环境变量配置：

```sh
$env:SITE_URL="https://你的域名/"
pnpm build
```

国内部署建议见 `docs/deploy-cn.md`。

## GitHub Pages

仓库推到 GitHub 后，在仓库 Settings -> Pages 里把 Source 设为 `GitHub Actions`。之后每次推送 `main` 分支都会自动构建并发布。

如果仓库名是 `你的用户名.github.io`，访问地址是：

```txt
https://你的用户名.github.io/
```

如果仓库名是普通仓库，例如 `blog`，访问地址是：

```txt
https://你的用户名.github.io/blog/
```

## 文章 Frontmatter

```yaml
---
title: 我的第一篇文章
published: 2026-05-10
description: 文章摘要
image: ""
tags: [技术, 博客]
category: 技术
draft: false
lang: zh_CN
---
```

## 上游

模板来源：`saicaca/fuwari`，MIT License。
