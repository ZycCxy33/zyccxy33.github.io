# 博客 URL 配置指南

## 重要：更新你的博客 URL

为了确保博客在 GitHub Pages 上正常工作，你需要更新 `_config.yml` 中的 URL 设置。

### 如何更新 URL

1. **打开 `_config.yml` 文件**
2. **找到第 16 行**：`url: http://example.com`
3. **替换为你的 GitHub Pages 地址**：
   ```yaml
   url: https://yourname.github.io
   ```
   将 `yourname` 替换为你的 GitHub 用户名

### 示例配置

如果你的 GitHub 用户名是 `johnsmith`，则设置为：
```yaml
url: https://johnsmith.github.io
```

### 为什么需要设置正确的 URL

- **确保链接正确**：文章和页面的链接会基于此 URL 生成
- **SEO 优化**：搜索引擎需要正确的 URL 来索引你的内容
- **社交媒体分享**：分享时显示正确的链接
- **RSS 订阅**：RSS 源会使用此 URL

### 更新步骤

1. **编辑配置文件**
   ```bash
   # 在博客根目录下
   nano _config.yml
   # 或者使用你喜欢的编辑器
   ```

2. **修改 URL**
   ```yaml
   # 从
   url: http://example.com
   
   # 改为
   url: https://yourname.github.io
   ```

3. **保存并推送**
   ```bash
   git add _config.yml
   git commit -m "Update blog URL"
   git push origin main
   ```

### 如果使用自定义域名

如果你有自己的域名，设置为：
```yaml
url: https://your-domain.com
```

### 验证配置

更新配置后，可以：
1. 本地测试：`hexo server`
2. 检查生成的链接是否正确
3. 重新部署到 GitHub Pages

### 注意事项

- URL 必须以 `http://` 或 `https://` 开头
- 不要在 URL 末尾添加斜杠
- 确保 URL 格式正确，否则可能导致链接错误
- 更改 URL 后需要重新部署才能生效