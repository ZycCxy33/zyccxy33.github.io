# 我的个人博客部署指南

## 本地开发

1. **启动本地服务器**
   ```bash
   hexo server
   ```
   访问 http://localhost:4000 查看博客

2. **创建新文章**
   ```bash
   hexo new post "文章标题"
   ```

3. **创建新页面**
   ```bash
   hexo new page "页面名称"
   ```

## GitHub 部署

### 自动部署设置

1. **创建 GitHub 仓库**
   - 创建名为 `username.github.io` 的仓库（username 是你的 GitHub 用户名）
   - 或者创建任意名称的仓库，博客将部署到 GitHub Pages

2. **推送代码到 GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/username/blog-repo.git
   git push -u origin main
   ```

3. **启用 GitHub Pages**
   - 进入仓库 Settings
   - 找到 Pages 部分
   - Source 选择 GitHub Actions
   - 保存后自动部署开始

### 自定义域名设置

1. **购买域名**（可选）
   - 推荐域名注册商：阿里云、腾讯云、Namecheap 等

2. **配置 DNS**
   - 添加 CNAME 记录指向 `username.github.io`
   - 或添加 A 记录指向 GitHub Pages IP 地址

3. **在博客配置中设置域名**
   - 在 `_config.yml` 中更新 `url` 字段

## 博客管理

### 目录结构
```
my-blog/
├── source/           # 源文件
│   ├── _posts/       # 博客文章
│   ├── about/        # 关于页面
│   └── ...
├── themes/           # 主题文件
├── _config.yml       # 主配置文件
└── package.json      # 依赖配置
```

### 常用命令
```bash
hexo clean           # 清理缓存
hexo generate        # 生成静态文件
hexo server          # 启动本地服务器
hexo deploy          # 部署到远程服务器
```

## 下一步

1. **自定义主题**
   - 修改主题配置文件
   - 调整颜色、字体、布局等

2. **添加功能**
   - 评论系统（Gitalk、Valine）
   - 搜索功能
   - 统计分析

3. **内容创作**
   - 定期发布文章
   - 与读者互动

## 注意事项

- 确保文章的 front matter 格式正确
- 定期备份博客源码
- 及时更新 Hexo 和主题版本
- 遵守 GitHub Pages 使用条款