# hiktoop's blog

Built with Hugo + Stack theme, deployed on GitHub Pages.

## 写文章

```powershell
hugo new post/my-post-title/index.md
```

编辑 `content/post/my-post-title/index.md`：

```markdown
+++
title = "文章标题"
date = "2026-05-10"
description = "简短描述"
categories = ["分类1"]
tags = ["标签1", "标签2"]
draft = false
+++

正文写这里...
```

- `draft: true` 时文章不会发布，设为 `false` 才会上线
- 图片放在文章目录下（index.md 同级），用相对路径引用：`![alt](image.jpg)`

## 本地预览

```powershell
hugo server -D
```

打开 http://localhost:1313，保存文件后自动刷新。

- `-D` 会显示草稿（draft: true），不加则只显示发布状态的文章

## 创建独立页面

```powershell
hugo new page/my-page/index.md
```

编辑后在 frontmatter 加 `menu: main` 可加入导航栏：

```yaml
menu:
    main:
        weight: -50
        params:
            icon: file
```

## 添加静态文件

图片、CSS、JS 等放到 `static/` 目录下，构建后自动复制到网站根目录：

```
static/img/avatar.jpg   →   https://hiktoop.github.io/img/avatar.jpg
```

## 部署上线

```powershell
git add -A
git commit -m "描述你的改动"
git push
```

推送后 GitHub Actions 自动构建并部署到 https://hiktoop.github.io/。
