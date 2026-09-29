# 个人学术主页（Jekyll + GitHub Pages）

带 News、论文列表、博客的个人主页。不需要写前端，日常更新只改文本文件。

## 一、部署上线（约 10 分钟）

1. 在 GitHub 新建一个**公开**仓库，名字必须是 `你的用户名.github.io`。
2. 把本文件夹里的所有文件上传到仓库（网页端直接拖拽即可，或用 git push）。
3. 进入仓库 **Settings → Pages**，Source 选 **Deploy from a branch**，Branch 选 `main`、文件夹选 `/ (root)`，保存。
4. 等 1～2 分钟，访问 `https://你的用户名.github.io` 就能看到网站。在仓库的 **Actions** 标签页可以看到构建进度和报错。

## 二、改成你自己的信息

| 想改什么 | 改哪个文件 |
|---|---|
| 名字、职位、学校、邮箱、社交链接、导航 | `_config.yml` |
| 首页自我介绍 | `index.md` |
| 头像 | 把照片放进 `assets/img/`，再改 `_config.yml` 里的 `avatar` |
| 新闻 | `_data/news.yml`（新的写在最上面） |
| 论文 | `_data/publications.yml`（`selected: true` 会上首页） |
| 博客 | 在 `_posts/` 新建 `YYYY-MM-DD-title.md` |
| CV | 把 PDF 命名为 `cv.pdf` 放进 `assets/` |
| 配色、字体 | `assets/css/style.css` 顶部的变量 |

`_config.yml` 里的 `url` 也要改成你自己的地址。注意：**改 `_config.yml` 后要重新 push 才会生效**，本地预览时也要重启服务。

## 三、本地预览（可选）

需要先装 Ruby（macOS 建议用 Homebrew 装新版 Ruby；Windows 用 RubyInstaller）。

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

然后浏览器打开 http://localhost:4000 。改文件后页面会自动重新生成，刷新即可。

## 四、常见问题

- **网站 404**：确认仓库名是 `用户名.github.io`，并且 Pages 设置里选了 main 分支。
- **push 后没变化**：去 Actions 看构建是否失败，最常见的原因是 YAML 缩进错误（必须用空格，不能用 Tab），或者文本里含冒号却没加引号。
- **博客不显示**：文件名必须以日期开头，且日期不能晚于今天（Jekyll 默认不发布未来日期的文章）。
- **公式不显示**：在该文章开头加 `math: true`。
- **绑定自己的域名**：在 Settings → Pages 的 Custom domain 填入域名，并在域名服务商处添加 CNAME 记录指向 `用户名.github.io`。
