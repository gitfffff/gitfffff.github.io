# 国内可访问部署清单

这个博客是 Astro 静态站点，构建后产物在 `dist/`。只要静态托管服务能直接提供 `dist/` 里的文件，就可以部署。

## 本地构建

```sh
pnpm install
pnpm build
```

如果有正式域名，构建时设置：

```sh
$env:SITE_URL="https://你的域名/"
pnpm build
```

如果部署在子路径，例如 `https://example.com/blog/`，再设置：

```sh
$env:BASE_PATH="/blog/"
```

## 推荐部署路线

1. 阿里云 OSS + CDN：适合国内访问和备案域名，静态文件直接上传 `dist/`。
2. 腾讯云 COS + CDN：同样适合国内访问，控制台可开启静态网站托管。
3. 自有云服务器 + Nginx：控制力最高，适合已经有服务器的情况。

## 注意事项

- 尽量不要依赖海外 CDN、Google Fonts 或远程图片；当前模板字体和图标都通过 npm 打包进站点。
- 国内 CDN 通常要求域名备案。
- GitHub Pages 可以作为备用发布渠道，但国内访问稳定性不如国内对象存储/CDN。
- 评论和统计服务后续再加，优先选择国内可访问或自托管方案。

## 先用 GitHub Pages

项目已包含 `.github/workflows/deploy-pages.yml`。仓库推到 GitHub 后，在 Settings -> Pages 中选择 `GitHub Actions` 作为发布源即可。

如果使用 `username.github.io` 仓库，站点会发布在根路径 `/`。如果使用普通仓库，例如 `blog`，工作流会自动使用 `/blog/` 子路径构建。
