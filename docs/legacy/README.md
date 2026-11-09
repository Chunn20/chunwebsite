# 历史构建配置

此目录保存旧的 GitHub Pages 原生构建方案：`_config_github_pages.yml` 和 `Gemfile.github-pages`。

当前网站使用根目录 `Gemfile`、`_config.yml`、`_config_prod.yml`，通过 `.github/workflows/docker-deploy.yml` 在 Docker 中构建，再将静态文件发布到 `gh-pages`。此处文件不参与构建，也不会发布到网站。

保留这些文件用于查阅历史，不应直接替换当前配置：原生 GitHub Pages 支持的插件集合与本站不同。
