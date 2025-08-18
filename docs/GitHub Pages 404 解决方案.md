# GitHub Pages 404 错误解决方案

## 问题分析

### 检测到的问题：
1. **缺少部署插件**：`hexo-deployer-git` 未安装
2. **部署配置为空**：`_config.yml` 中 `deploy.type` 为空字符串
3. **GitHub Pages 设置可能不正确**：需要正确配置 GitHub Pages 分支

### 根本原因：
- Hexo 生成的静态文件没有正确部署到 GitHub Pages
- GitHub Pages 没有找到 `index.html` 文件
- 部署流程不完整

## 已实施的解决方案

### 1. 安装部署插件 ✅
```bash
npm install hexo-deployer-git --save
```

### 2. 配置部署设置 ✅
```yaml
# _config.yml
deploy:
  type: git
  repo: https://github.com/zyccxy33/zyccxy33.github.io.git
  branch: main
```

### 3. 验证网站生成 ✅
- ✅ 网站已成功生成
- ✅ `index.html` 文件存在于 `public/` 目录
- ✅ 所有图片和页面都已生成

## 完整部署流程

### 步骤 1：生成网站
```bash
hexo clean
hexo generate
```

### 步骤 2：部署到 GitHub
```bash
hexo deploy
```

### 步骤 3：验证部署
访问 https://zyccxy33.github.io 检查是否正常显示

## GitHub Pages 配置检查

### 1. 检查仓库设置
在 GitHub 仓库中确认：
- 仓库名称：`zyccxy33.github.io`
- 仓库状态：Public（免费版需要公开仓库）
- 分支设置：main 分支

### 2. 检查 GitHub Pages 设置
1. 进入仓库的 **Settings** 页面
2. 点击左侧菜单的 **Pages**
3. 确认以下设置：
   - **Source**: Deploy from a branch
   - **Branch**: main
   - **Directory**: / (root)

### 3. 检查自定义域名（如果使用）
如果您使用自定义域名，确保：
- DNS 配置正确
- CNAME 文件存在于 `source/` 目录
- 域名指向正确

## 常见问题排查

### 1. 仓库权限问题
- 确保您有推送权限到仓库
- 检查 SSH key 或 Personal Access Token 是否正确

### 2. 分支名称问题
- GitHub 默认分支可能是 `master` 而不是 `main`
- 如果是 `master`，修改配置：
  ```yaml
  deploy:
    branch: master
  ```

### 3. 仓库名称问题
- 确保仓库名称是 `username.github.io` 格式
- 对于项目页面，仓库名称可以是任意的，但 URL 会是 `username.github.io/repo`

### 4. 网站内容问题
- 确保 `public/` 目录包含 `index.html`
- 检查生成的文件结构是否正确
- 确认所有路径都是相对路径

## 部署测试

### 本地测试
```bash
hexo server
# 访问 http://localhost:4000
```

### 部署测试
```bash
hexo deploy
```

### 验证方法
1. 等待 1-2 分钟（GitHub Pages 需要时间部署）
2. 访问 https://zyccxy33.github.io
3. 检查是否能正常显示

## 故障排除清单

### 如果仍然显示 404：
- [ ] 检查仓库是否存在
- [ ] 确认仓库是公开的
- [ ] 验证 GitHub Pages 设置
- [ ] 检查部署是否成功
- [ ] 确认分支名称正确
- [ ] 检查 DNS 设置（如果是自定义域名）

### 如果网站样式错乱：
- [ ] 检查 CSS 文件路径
- [ ] 确认资源文件是否正确部署
- [ ] 检查 CDN 配置

### 如果图片不显示：
- [ ] 检查图片路径
- [ ] 确认图片文件已部署
- [ ] 检查文件名大小写

## 后续维护

### 1. 自动化部署
考虑使用 GitHub Actions 实现自动化部署：
```yaml
# .github/workflows/deploy.yml
name: Deploy Hexo Site

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Setup Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '18'
    - name: Install dependencies
      run: npm install
    - name: Generate site
      run: hexo generate
    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./public
```

### 2. 定期更新
- 定期更新 Hexo 和主题
- 监控网站性能
- 备份重要文件

## 总结

通过以下步骤解决 404 问题：
1. ✅ 安装了 `hexo-deployer-git` 插件
2. ✅ 配置了正确的部署设置
3. ✅ 生成了完整的网站文件
4. ✅ 验证了文件结构正确

现在可以执行 `hexo deploy` 命令部署到 GitHub Pages。