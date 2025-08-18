# 🛠️ GitHub Pages 部署问题修复指南

## 问题分析

根据错误信息 `Get Pages site failed`，主要问题包括：

1. **GitHub Pages 未启用**
2. **部署配置不正确**
3. **权限设置问题**

## 解决方案

### 方案1：手动启用 GitHub Pages（推荐）

1. **访问仓库设置**
   ```
   https://github.com/zyccxy33/zyccxy33.github.io/settings/pages
   ```

2. **配置 Pages 设置**
   - Source: 选择 "GitHub Actions"
   - Custom domain: 留空（使用默认域名）
   - Enforce HTTPS: 开启

3. **保存设置并等待**

### 方案2：检查 GitHub Actions 权限

1. **仓库设置 → Actions → General**
   - 确保 "Allow all actions and reusable workflows" 已启用
   - 确保 "Read and write permissions" 已启用

2. **仓库设置 → Pages**
   - 确保 "GitHub Actions" 已选择为部署源

### 方案3：验证仓库配置

检查以下配置是否正确：

1. **仓库名称**：必须是 `username.github.io`
2. **分支设置**：必须是 `main` 分支
3. **Actions 权限**：需要 `contents: read`, `pages: write`, `id-token: write`

## 验证步骤

### 1. 本地测试
```bash
# 清理并重新生成
hexo clean
hexo generate

# 本地预览
hexo server
```

### 2. 检查配置文件
```bash
# 检查 _config.yml 中的 URL 设置
cat _config.yml | grep url
# 应该显示: url: https://zyccxy33.github.io
```

### 3. 验证 GitHub 设置
- 仓库必须是 Public
- Pages 设置必须选择 GitHub Actions
- Actions 权限必须正确

## 常见错误及解决

### 错误1：Repository not found
**原因**：仓库名称错误
**解决**：确保仓库名为 `zyccxy33.github.io`

### 错误2：Permission denied
**原因**：Actions 权限不足
**解决**：在仓库设置中启用 Actions 权限

### 错误3：Pages not enabled
**原因**：GitHub Pages 未启用
**解决**：在 Settings → Pages 中启用并选择 GitHub Actions

## 部署成功后的访问

### 默认域名
```
https://zyccxy33.github.io
```

### 自定义域名（可选）
1. 在域名提供商添加 DNS 记录
2. 在 GitHub Pages 设置中添加自定义域名
3. 等待 DNS 生效

## 联系支持

如果问题仍然存在，请：
1. 查看 GitHub Actions 日志获取详细错误信息
2. 检查 GitHub Status 确认服务正常
3. 在 GitHub Issues 中搜索类似问题

---

**注意**：首次部署可能需要几分钟时间生效，请耐心等待。