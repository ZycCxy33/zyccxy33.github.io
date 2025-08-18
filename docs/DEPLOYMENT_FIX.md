# GitHub Actions 部署故障排除指南

## 问题：The process '/usr/bin/git' failed with exit code 128

### 错误原因分析
这个错误通常由以下原因引起：
1. **Git 权限问题** - Actions 没有足够的权限执行 Git 操作
2. **Token 权限不足** - GITHUB_TOKEN 权限不够
3. **Git 配置问题** - 缺少用户信息配置

### 已实施的解决方案

#### 1. 更新了 GitHub Actions 配置
- 添加了必要的权限设置
- 使用了最新的 GitHub Pages Actions
- 配置了正确的用户信息

#### 2. 新配置的特点
- 使用 `actions/deploy-pages@v4` 替代 `peaceiris/actions-gh-pages@v3`
- 添加了 `permissions` 部分，明确权限范围
- 使用 `submodules: recursive` 确保子模块正确下载
- 添加了 `NODE_ENV: production` 环境变量

### 下一步操作

#### 1. 提交并推送新的配置
```bash
git add .github/workflows/deploy.yml
git commit -m "Fix GitHub Actions deployment configuration"
git push origin main
```

#### 2. 检查部署状态
- 访问 GitHub 仓库的 Actions 页面
- 查看 "Deploy Hexo Blog" 工作流
- 确认是否成功运行

#### 3. 如果仍然失败，尝试以下步骤

##### 方案 A：手动触发部署
1. 进入仓库 Settings → Pages
2. 确保 Source 设置为 "GitHub Actions"
3. 点击 "Re-run all jobs" 重新运行

##### 方案 B：检查仓库权限
1. 进入仓库 Settings → Actions → General
2. 确保 "Allow all actions and reusable workflows" 已启用
3. 检查 "Workflow permissions" 设置为 "Read and write permissions"

##### 方案 C：清理并重新部署
```bash
# 清理本地缓存
hexo clean

# 重新生成
hexo generate

# 提交更改
git add .
git commit -m "Clean and regenerate"
git push origin main
```

### 预期结果

新的配置应该能够：
- 正确处理 Git 权限问题
- 使用更稳定的部署方式
- 提供更好的错误信息

### 如果问题仍然存在

请提供以下信息：
1. 完整的错误日志
2. GitHub Actions 的运行状态
3. 仓库的设置信息

### 备用方案

如果新的配置仍然失败，可以尝试：

#### 1. 使用传统部署方式
```yaml
- name: Deploy to GitHub Pages
  uses: peaceiris/actions-gh-pages@v3
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}
    publish_dir: ./public
    destination_dir: ./
    user_name: ${{ github.actor }}
    user_email: ${{ github.actor }}@users.noreply.github.com
```

#### 2. 创建 Personal Access Token
1. 进入 GitHub Settings → Developer settings → Personal access tokens
2. 创建新的 token，赋予 `repo` 权限
3. 在仓库 Settings → Secrets and variables → Actions 中添加 token
4. 在 Actions 中使用自定义 token

### 监控部署

部署成功后，你应该看到：
- ✅ 绿色的勾号表示成功
- 📊 部署统计信息
- 🌐 博客在线可访问

记住，有时候需要等待几分钟才能看到部署结果。