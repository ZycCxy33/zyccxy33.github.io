# GitHub Actions 部署状态检查指南

## 如何检查部署状态

### 1. 访问 GitHub Actions 页面
1. 进入你的 GitHub 仓库
2. 点击顶部导航栏的 "Actions" 选项卡
3. 查看最近的 "Deploy Hexo Blog" 工作流

### 2. 理解工作流状态
- ✅ **绿色勾号**：部署成功
- 🔄 **蓝色圆圈**：正在进行中
- ❌ **红色叉号**：部署失败
- ⚠️ **黄色三角**：警告但不影响部署

### 3. 查看部署日志
如果部署失败，点击工作流查看详细日志：
- 检查 "Setup Node.js" 步骤
- 查看 "Install dependencies" 步骤
- 查看 "Generate static files" 步骤
- 查看 "Deploy to GitHub Pages" 步骤

### 4. 常见问题排查

#### 问题 1：Node.js 版本不兼容
- 确保使用 Node.js 18 或更高版本
- 检查 package.json 中的依赖版本

#### 问题 2：主题安装失败
- 确认 hexo-theme-next 已正确安装
- 检查 _config.yml 中的主题配置

#### 问题 3：权限问题
- 确保 GITHUB_TOKEN 有写入权限
- 检查仓库设置中的 Actions 权限

## 下一步操作

### 如果部署成功 ✅
1. 进入仓库 Settings → Pages
2. 查看博客 URL
3. 点击链接访问你的博客

### 如果部署失败 ❌
1. 复制错误日志信息
2. 根据错误类型修复问题
3. 重新推送代码触发部署

## 预期结果

部署成功后，你的博客将在以下地址可用：
- `https://yourname.github.io`

## 获取帮助

如果遇到问题，可以：
1. 查看 GitHub 官方文档
2. 搜索 Hexo 社区论坛
3. 在评论区提问并提供错误信息