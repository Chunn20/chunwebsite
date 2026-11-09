# Xinchun Li · 个人学术网站

基于 [al-folio](https://github.com/alshedivat/al-folio) 和 Jekyll 的个人网站，展示个人介绍、研究项目、博客与联系方式。

网站地址：**https://chunn20.github.io/chunwebsite/**

## 当前外观

采用 Academic Pages 风格的双栏布局：顶部导航、左侧个人资料、右侧正文；窄屏下个人资料移到正文上方。底层仍是现有 al-folio/Jekyll，并未整套迁移 Academic Pages 主题。

- `assets/css/academic.css`：统一的外观覆盖层，控制字体、颜色、双栏布局及移动端样式。
- `_includes/author-sidebar.liquid`：个人信息侧栏，读取 `_config.yml` 的姓名、头像、单位、邮箱和简历路径。
- `_layouts/default.liquid`：所有使用默认布局的页面共享的双栏结构。
- `_layouts/about.liquid`：首页正文布局；头像和联系链接统一放在侧栏。

页面内容、原有网址与发布流程保持不变。深浅色切换仍可用，页脚改为跟随内容。

## 日常更新入口

| 要修改的内容 | 文件或目录 |
| --- | --- |
| 首页介绍与头像设置 | `index.md` |
| 关于我 | `_pages/aboutme.en.md` |
| 研究页面 | `_pages/research.en.md`、`_projects/`、`_talks/` |
| 联系方式 | `_pages/contact.en.md` |
| 博客文章 | `_posts/`，使用 `YYYY-MM-DD-title.md` 命名 |
| 头像、图片 | `assets/img/` |
| 简历 PDF | `assets/pdf/`；下载按钮路径在 `_config.yml` 的 `cv_button_url` |
| 站点名称、邮箱、社交账号、功能开关 | `_config.yml` |
| 导航显示与排序 | `_pages/` 中各页面开头的 `nav`、`nav_order` |

页面和文章开头的 `---` 区块是元数据。修改正文时保留此区块；不要随意修改已有 `permalink`，以免原链接失效。

## 目录说明

- `_pages/`、`_posts/`、`_projects/`、`_talks/`：网站内容。
- `_news/`、`_books/`：保留的模板示例，分别对应当前关闭的公告功能和未配置的书评集合。
- `_data/`、`_bibliography/`：结构化数据与参考文献。
- `_layouts/`、`_includes/`、`_sass/`、`_plugins/`、`_scripts/`：主题布局、样式及构建代码。
- `assets/`：网站静态资源。
- `.github/workflows/docker-deploy.yml`：当前线上构建与发布流程。
- `bin/`、`Dockerfile`、`docker-compose*.yml`：本地 Docker 预览相关文件。
- `docs/template/`：归档的上游模板文档、预览图与历史 Lighthouse 报告。
- `docs/legacy/`：未用于当前发布流程的旧 GitHub Pages 构建配置。

`docs/` 和开发工具文件已从网站构建输出中排除。归档资料仅供参考，维护本站以本 README 和当前工作流为准。

## 本地预览

需要先安装并启动 Docker Desktop。在仓库根目录运行：

```sh
docker compose up
```

访问 **http://localhost:8080/chunwebsite/**。结束预览可按 `Ctrl+C`，再运行 `docker compose down`。

也可以在已安装 Ruby、Bundler 及所需系统依赖的环境中使用：

```sh
bundle install
bundle exec jekyll serve --host 127.0.0.1 --port 8080
```

涉及 notebook 的页面还需要 Jupyter。依赖以 `Gemfile`、`Gemfile.lock` 和部署工作流为准；`package.json` 仅提供格式化工具，不是网站启动入口。

## 发布流程

1. 修改 `main` 分支的源文件，检查后提交并推送。
2. GitHub Actions 的 **Deploy with Docker** 使用 `_config.yml,_config_prod.yml` 构建网站。
3. 构建产物由工作流写入 `gh-pages` 分支。
4. GitHub Pages 从 **`gh-pages` → `/ (root)`** 发布网站。

不要直接编辑 `gh-pages` 分支或提交本地 `_site/`，它们是生成结果。生产配置 `_config_prod.yml` 保留为线上覆盖层；如果更换网址，需要同步修改两份配置中的 `url` 和 `baseurl`。

## 网站打不开时

- 确认访问的是完整地址 `https://chunn20.github.io/chunwebsite/`。
- 在仓库 **Settings → Pages** 检查 Source 为 **Deploy from a branch**，分支为 **gh-pages**，目录为 **/ (root)**。
- 在 **Actions** 查看构建和 Pages 部署是否成功；刚保存设置时需等待部署完成。
- 如果将仓库改为私有，先确认账户套餐支持私有仓库的 GitHub Pages。

## 模板与许可

保留上游 [MIT 许可证](LICENSE)。原模板说明见 [docs/template/README.md](docs/template/README.md)，其安装说明可能与本站当前配置不同。
