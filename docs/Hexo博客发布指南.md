# Hexo 博客文章发布指南

## 概述
本指南介绍如何在本地撰写包含图片的 Markdown 文档，并发布到 Hexo 博客网站。

## 项目结构
```
my-blog/
├── source/
│   └── _posts/          # 博客文章存放目录
├── public/              # 生成的静态网站
├── themes/              # 主题文件
├── _config.yml          # Hexo 配置文件
└── package.json         # 项目依赖
```

## 发布步骤

### 1. 创建文章
将您的 Markdown 文章文件放置在 `source/_posts/` 目录下。

```bash
# 示例：将文章复制到 _posts 目录
cp 您的文章.md source/_posts/
```

### 2. 处理图片
Hexo 提供了多种处理图片的方式：

#### 方式一：使用资源文件夹（推荐）
1. 在 `_config.yml` 中设置 `post_asset_folder: true`
2. 创建与文章同名的文件夹存放图片
3. 在文章中使用相对路径引用图片

```
source/_posts/
├── 我的文章/
│   ├── image1.jpg
│   └── image2.png
└── 我的文章.md
```

在 Markdown 中引用图片：
```markdown
![图片描述](我的文章/image1.jpg)
```

#### 方式二：使用绝对路径
将图片放在 `source/images/` 目录下，然后在文章中使用：
```markdown
![图片描述](/images/image1.jpg)
```

#### 方式三：使用图床服务
将图片上传到图床服务（如 GitHub、七牛云等），然后在文章中使用 URL 引用。

### 3. 文章 Front Matter
在文章开头添加 Front Matter 信息：

```markdown
---
title: 文章标题
date: 2025-08-18 10:00:00
categories: 分类名称
tags: [标签1, 标签2]
description: 文章描述
---
```

### 4. 生成网站
```bash
# 进入博客目录
cd my-blog

# 清理缓存
npm run clean

# 生成静态网站
npm run build
```

### 5. 本地预览
```bash
# 启动本地服务器
npm run server

# 访问 http://localhost:4000 查看效果
```

### 6. 部署到 GitHub Pages
1. 确保已配置 `_config.yml` 中的部署设置
2. 安装部署插件：
```bash
npm install hexo-deployer-git --save
```

3. 在 `_config.yml` 中添加部署配置：
```yaml
deploy:
  type: git
  repo: https://github.com/username/username.github.io.git
  branch: main
```

4. 部署网站：
```bash
npm run deploy
```

## 图片处理最佳实践

### 1. 图片优化
- 使用适当的图片格式（JPEG 适用于照片，PNG 适用于图标）
- 压缩图片以减少加载时间
- 考虑使用 WebP 格式以获得更好的压缩效果

### 2. 图片大小
- 建议图片宽度不超过 1200px
- 文件大小控制在 500KB 以内
- 使用工具如 TinyPNG 压缩图片

### 3. 图片命名
- 使用有意义的文件名
- 避免使用中文和特殊字符
- 使用小写字母和连字符

## 常见问题解决

### 1. 图片无法显示
- 检查图片路径是否正确
- 确保图片文件存在
- 检查文件名大小写
- 确认 `post_asset_folder` 设置

### 2. 部署失败
- 检查 GitHub 仓库权限
- 确认分支名称正确
- 检查网络连接

### 3. 样式问题
- 检查主题配置
- 确认 CSS 文件正确加载
- 检查 Markdown 语法

## 进阶技巧

### 1. 使用 Hexo 标签插件
```markdown
{% asset_img image.jpg 图片描述 %}
{% asset_img image.jpg 500 300 图片描述 %}
```

### 2. 图片懒加载
在主题配置中启用图片懒加载以提高页面加载速度。

### 3. 响应式图片
使用 HTML5 的 `<picture>` 标签或 CSS 媒体查询实现响应式图片。

## 总结
1. 将 Markdown 文章放入 `source/_posts/` 目录
2. 合理组织图片资源
3. 添加必要的 Front Matter
4. 生成并预览网站
5. 部署到 GitHub Pages

按照以上步骤，您就可以成功发布包含图片的博客文章了。