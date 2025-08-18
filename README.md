# 🌟 我的个人博客

<div align="center">

![Hexo](https://img.shields.io/badge/Hexo-7.0+-0E83C8?style=for-the-badge&logo=hexo&logoColor=white)
![Next Theme Badge](https://img.shields.io/badge/Next-Theme-0070f3?style=for-the-badge&logo=next.js&logoColor=white)
![GitHub Pages](https://img.shields.io/badge/GitHub_Pages-222222?style=for-the-badge&logo=github&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

**基于 Hexo + Next 主题构建的个人博客，部署在 GitHub Pages**

[🏠 访问博客](https://zyccxy33.github.io) • [📖 完整指南](./BLOG_COMPLETE_GUIDE.md) • [🚀 部署指南](./DEPLOYMENT.md) • [🛠️ 故障排除](./TROUBLESHOOTING.md)

</div>

---

## 📋 目录

- [🌟 关于博客](#-关于博客)
- [🚀 快速开始](#-快速开始)
- [📁 项目结构](#-项目结构)
- [🛠️ 技术栈](#-技术栈)
- [🎯 功能特性](#-功能特性)
- [📝 内容创作](#-内容创作)
- [🌐 部署说明](#-部署说明)
- [📚 文档指南](#-文档指南)
- [🤝 贡献指南](#-贡献指南)
- [📄 许可证](#-许可证)

---

## 🌟 关于博客

欢迎来到我的个人博客！这是一个基于 [Hexo](https://hexo.io/) 静态网站生成器构建的现代化博客，使用 [Next](https://theme-next.js.org/) 主题，部署在 [GitHub Pages](https://pages.github.com/) 上。

### 博客特色

- 🎨 **现代化设计** - 使用 Next 主题，界面简洁美观
- ⚡ **极速加载** - 静态网站，访问速度快
- 📱 **响应式布局** - 完美适配桌面端和移动端
- 🔍 **SEO 优化** - 内置 SEO 优化，提高搜索排名
- 🌙 **夜间模式** - 支持深色主题，保护眼睛
- 💬 **评论系统** - 集成评论功能，便于交流
- 📊 **访问统计** - 内置访问量统计

---

## 🚀 快速开始

### 环境要求

- [Node.js](https://nodejs.org/) (v18 或更高版本)
- [Git](https://git-scm.com/)
- [GitHub 账号](https://github.com/)

### 本地运行

1. **克隆仓库**
   ```bash
   git clone https://github.com/zyccxy33/zyccxy33.github.io.git
   cd zyccxy33.github.io
   ```

2. **安装依赖**
   ```bash
   npm install
   ```

3. **启动本地服务器**
   ```bash
   hexo server
   ```

4. **访问博客**
   打开浏览器访问 [http://localhost:4000](http://localhost:4000)

### 常用命令

```bash
# 创建新文章
hexo new post "文章标题"

# 创建新页面
hexo new page "页面名称"

# 清理缓存
hexo clean

# 生成静态文件
hexo generate

# 启动本地服务器
hexo server

# 部署到远程
hexo deploy
```

---

## 📁 项目结构

```
my-blog/
├── .github/                  # GitHub Actions 配置
│   └── workflows/              # 自动化工作流
│       └── deploy.yml          # 部署配置
├── source/                    # 源文件目录
│   ├── _posts/                 # 博客文章
│   ├── about/                  # 关于页面
│   ├── tags/                   # 标签页面
│   └── categories/             # 分类页面
├── themes/                    # 主题文件
│   └── next/                   # Next 主题
├── scaffolds/                  # 文章模板
├── public/                     # 生成的静态文件
├── _config.yml                 # Hexo 主配置文件
├── package.json               # 项目依赖配置
└── 各种文档和指南             # 详细使用指南
```

### 核心文件说明

| 文件 | 作用 |
|------|------|
| `_config.yml` | Hexo 主配置文件，控制整个博客的设置 |
| `package.json` | 项目依赖和脚本配置 |
| `.github/workflows/deploy.yml` | GitHub Actions 自动部署配置 |
| `source/_posts/` | 存放所有博客文章 |
| `themes/next/` | Next 主题文件 |
| `BLOG_COMPLETE_GUIDE.md` | 完整博客使用指南 |

---

## 🛠️ 技术栈

### 核心技术

| 技术 | 版本 | 说明 |
|------|------|------|
| [Hexo](https://hexo.io/) | ^7.0.0 | 快速、简洁且高效的静态网站生成器 |
| [Next Theme](https://theme-next.js.org/) | ^8.24.0 | 优雅、强大的 Hexo 主题 |
| [GitHub Pages](https://pages.github.com/) | - | 免费、稳定的静态网站托管服务 |
| [GitHub Actions](https://github.com/features/actions) | - | 自动化 CI/CD 部署流程 |

### 开发工具

| 工具 | 用途 |
|------|------|
| Node.js | JavaScript 运行环境 |
| npm | 包管理器 |
| Git | 版本控制 |
| Markdown | 内容编写格式 |
| EJS | 模板引擎 |
| Stylus | CSS 预处理器 |

### 部署架构

```mermaid
graph LR
    A[本地写作] --> B[Git 推送]
    B --> C[GitHub Actions]
    C --> D[Hexo 构建]
    D --> E[静态文件]
    E --> F[GitHub Pages]
    F --> G[用户访问]
```

---

## 🎯 功能特性

### 🎨 界面设计

- **现代化 UI** - 简洁、美观的用户界面
- **响应式设计** - 完美适配各种设备
- **多种主题** - 支持多种主题风格切换
- **夜间模式** - 保护眼睛的深色主题
- **字体优化** - 优化的中英文字体显示

### 📝 内容管理

- **Markdown 支持** - 使用 Markdown 编写内容
- **文章分类** - 支持文章分类管理
- **标签系统** - 灵活的标签管理
- **搜索功能** - 内置文章搜索
- **代码高亮** - 语法高亮显示
- **数学公式** - 支持 LaTeX 数学公式

### 🔧 技术特性

- **SEO 优化** - 搜索引擎友好
- **性能优化** - 快速加载体验
- **HTTPS 支持** - 安全传输
- **PWA 支持** - 渐进式 Web 应用
- **RSS 订阅** - 支持 RSS 订阅
- **社交分享** - 社交媒体分享功能

### 💬 互动功能

- **评论系统** - 支持多种评论平台
- **访问统计** - 访问量统计和分析
- **友情链接** - 博客友链管理
- **联系表单** - 联系方式展示

---

## 📝 内容创作

### 文章格式

每篇文章使用 Markdown 格式，头部包含元信息：

```markdown
---
title: 文章标题
date: 2025-08-18 10:30:00
tags: [技术, 教程]
categories: [编程]
author: 作者名
description: 文章描述
---

# 文章标题

文章内容...
```

### 写作规范

1. **文件命名**：使用中文或英文，避免特殊字符
2. **图片处理**：图片放在 `source/images/` 目录
3. **代码块**：使用语言标识符实现语法高亮
4. **外链**：外部链接在新标签页打开
5. **摘要**：在 `<!-- more -->` 前写文章摘要

### 内容建议

- **原创性**：优先发布原创内容
- **价值性**：提供有价值的信息
- **定期更新**：保持一定的更新频率
- **互动性**：鼓励读者评论和交流

---

## 🌐 部署说明

### 自动部署

本项目使用 GitHub Actions 实现自动部署：

1. **触发条件**：代码推送到 `main` 分支
2. **构建过程**：自动安装依赖并生成静态文件
3. **部署目标**：GitHub Pages
4. **访问地址**：https://zyccxy33.github.io

### 手动部署

如需手动部署，可使用以下命令：

```bash
# 生成静态文件
hexo generate

# 部署到 GitHub Pages
hexo deploy
```

### 域名配置

如需使用自定义域名：

1. **购买域名**：在域名注册商处购买
2. **配置 DNS**：
   - CNAME 记录：`www` → `zyccxy33.github.io`
   - A 记录：`@` → `185.199.108.153`
3. **GitHub 设置**：在仓库 Settings → Pages 中设置域名

---

## 📚 文档指南

### 完整指南

- 📖 [**完整博客指南**](./BLOG_COMPLETE_GUIDE.md) - 最全面的博客使用指南
- 🚀 [**部署指南**](./DEPLOYMENT.md) - 详细的部署步骤说明
- 🛠️ [**故障排除**](./TROUBLESHOOTING.md) - 常见问题解决方案
- ✅ [**最终检查清单**](./FINAL_CHECKLIST.md) - 项目完成检查清单

### 快速参考

- [**GitHub Actions 检查**](./GITHUB_ACTIONS_CHECK.md) - Actions 状态检查
- [**GitHub Pages 设置**](./GITHUB_PAGES_SETUP.md) - Pages 配置指南
- [**URL 配置**](./URL_CONFIG_GUIDE.md) - URL 设置说明
- [**测试指南**](./TESTING_GUIDE.md) - 功能测试方法
- [**优化建议**](./OPTIMIZATION_GUIDE.md) - 博客优化建议
- [**部署修复**](./DEPLOYMENT_FIX.md) - 部署问题修复

### 新手必读

如果你是新手，建议按以下顺序阅读：

1. **[完整博客指南](./BLOG_COMPLETE_GUIDE.md)** - 了解整体概念
2. **[部署指南](./DEPLOYMENT.md)** - 学习如何部署
3. **[最终检查清单](./FINAL_CHECKLIST.md)** - 确保所有步骤完成
4. **[故障排除](./TROUBLESHOOTING.md)** - 解决可能的问题

---

## 🤝 贡献指南

### 欢迎贡献

如果你发现任何问题或有改进建议，欢迎：

1. **提交 Issue** - 在 [Issues](https://github.com/zyccxy33/zyccxy33.github.io/issues) 中报告问题
2. **提出建议** - 在 Discussions 中讨论改进想法
3. **贡献代码** - 提交 Pull Request 改进代码

### 开发流程

1. **Fork 仓库** - Fork 本仓库到你的 GitHub
2. **克隆仓库** - `git clone https://github.com/your-username/zyccxy33.github.io.git`
3. **创建分支** - `git checkout -b feature/your-feature`
4. **提交更改** - `git commit -m "Add your feature"`
5. **推送分支** - `git push origin feature/your-feature`
6. **创建 PR** - 在 GitHub 上创建 Pull Request

### 代码规范

- 使用 ESLint 进行代码检查
- 遵循现有代码风格
- 提交信息清晰明确
- 确保功能正常工作

---

## 📄 许可证

本项目采用 [MIT 许可证](LICENSE) - 查看文件了解详细信息。

### 许可证摘要

✅ **允许**
- 商业使用
- 修改
- 分发
- 私人使用

❌ **禁止**
- 追究责任
- 授权商标

📋 **要求**
- 包含许可证和版权声明
- 声明重大更改

---

## 🙏 致谢

### 技术栈

- [Hexo](https://hexo.io/) - 优秀的静态网站生成器
- [Next Theme](https://theme-next.js.org/) - 精美的 Hexo 主题
- [GitHub](https://github.com/) - 强大的代码托管平台
- [Node.js](https://nodejs.org/) - JavaScript 运行环境

### 工具和服务

- [Visual Studio Code](https://code.visualstudio.com/) - 优秀的代码编辑器
- [Git](https://git-scm.com/) - 版本控制系统
- [Markdown](https://www.markdownguide.org/) - 标记语言

### 社区

感谢所有为开源项目做出贡献的开发者！

---

## 📞 联系方式

如果你有任何问题或建议，欢迎通过以下方式联系我：

- 📧 **邮箱**：[your.email@example.com](mailto:your.email@example.com)
- 💼 **GitHub**：[zyccxy33](https://github.com/zyccxy33)
- 🌐 **博客**：[https://zyccxy33.github.io](https://zyccxy33.github.io)

---

<div align="center">

**⭐ 如果这个项目对你有帮助，请考虑给个 Star！**

![Star History](https://img.shields.io/github/stars/zyccxy33/zyccxy33.github.io?style=social)

</div>