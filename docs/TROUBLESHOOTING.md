# 博客部署故障排除指南

## 常见问题及解决方案

### 1. GitHub Actions 部署失败

#### 问题：Actions 工作流显示红色叉号
**可能原因：**
- Node.js 版本不兼容
- 依赖包安装失败
- 主题配置错误

**解决方案：**
1. 点击查看详细日志
2. 检查错误信息中的具体问题
3. 根据错误类型进行修复

#### 问题：npm install 失败
**错误信息：** `npm ERR! Cannot resolve dependency`
**解决方案：**
```bash
# 删除 node_modules 和 package-lock.json
rm -rf node_modules package-lock.json

# 重新安装依赖
npm install

# 测试本地构建
npm run build
```

#### 问题：主题未找到
**错误信息：** `Theme not found: next`
**解决方案：**
```bash
# 确保主题已安装
npm install hexo-theme-next

# 检查 _config.yml 中的主题配置
theme: next
```

### 2. GitHub Pages 配置问题

#### 问题：Pages 设置显示 404
**可能原因：**
- Source 设置错误
- 分支选择不正确
- 部署文件生成失败

**解决方案：**
1. 进入仓库 Settings → Pages
2. 确保 Source 设置为 "GitHub Actions"
3. 等待部署完成后刷新页面

#### 问题：自定义域名不生效
**可能原因：**
- DNS 配置错误
- CNAME 文件缺失
- HTTPS 证书未生成

**解决方案：**
1. 检查域名 DNS 设置
2. 在 source 目录创建 CNAME 文件
3. 等待 24-48 小时生效

### 3. 博客内容显示问题

#### 问题：页面样式缺失
**可能原因：**
- 主题资源未正确加载
- CSS 文件路径错误
- 静态资源生成失败

**解决方案：**
1. 检查主题配置
2. 重新生成静态文件
3. 清除浏览器缓存

#### 问题：文章链接 404
**可能原因：**
- 永久链接配置错误
- 文件名包含特殊字符
- URL 设置不正确

**解决方案：**
1. 检查 _config.yml 中的 permalink 设置
2. 确保文件名只包含字母、数字和中文
3. 更新 URL 配置

### 4. 本地测试问题

#### 问题：hexo server 启动失败
**错误信息：** `Port 4000 is already in use`
**解决方案：**
```bash
# 查找占用端口的进程
lsof -i :4000

# 终止进程
kill -9 <PID>

# 或者使用其他端口
hexo server -p 5000
```

#### 问题：本地预览正常，线上异常
**可能原因：**
- URL 配置不一致
- 路径大小写问题
- 缓存问题

**解决方案：**
1. 确保 _config.yml 中的 URL 正确
2. 检查文件名大小写
3. 清理缓存后重新部署

### 5. 调试步骤

#### 第一步：检查本地环境
```bash
# 清理缓存
hexo clean

# 重新生成
hexo generate

# 本地测试
hexo server
```

#### 第二步：检查配置文件
```bash
# 验证配置文件语法
hexo config

# 检查主题配置
cat _config.yml | grep theme
```

#### 第三步：查看详细日志
```bash
# 启用详细日志
hexo generate --debug

# 查看部署信息
hexo deploy --debug
```

### 6. 预防措施

#### 定期备份
```bash
# 备份重要文件
cp _config.yml _config.yml.backup
cp -r source source.backup
```

#### 版本控制
```bash
# 提交前检查状态
git status

# 小步提交，便于回滚
git add .
git commit -m "描述具体的更改"
```

#### 环境一致性
```bash
# 锁定依赖版本
npm shrinkwrap

# 记录 Node.js 版本
echo "18.19.1" > .nvmrc
```

### 7. 获取帮助的途径

#### 官方资源
- [Hexo 官方文档](https://hexo.io/docs/)
- [GitHub Pages 文档](https://docs.github.com/en/pages)
- [Next 主题文档](https://theme-next.js.org/)

#### 社区支持
- GitHub Issues
- Stack Overflow
- 技术论坛和社区

#### 常用搜索关键词
- "Hexo GitHub Pages deployment failed"
- "Hexo theme not found"
- "GitHub Pages custom domain not working"

### 8. 紧急恢复方案

#### 如果博客完全无法访问
1. 检查 GitHub 仓库是否正常
2. 验证 GitHub Pages 服务状态
3. 考虑回滚到上一个正常版本

#### 如果主题出现问题
1. 切换到默认主题测试
2. 重新安装主题
3. 检查主题配置文件

#### 如果内容丢失
1. 检查 Git 历史记录
2. 从本地恢复文件
3. 从搜索引擎缓存找回内容

## 快速检查清单

- [ ] GitHub Actions 是否成功运行
- [ ] GitHub Pages 是否正确配置
- [ ] _config.yml 中的 URL 是否正确
- [ ] 主题是否正确安装和配置
- [ ] 所有文件是否已推送到 GitHub
- [ ] 浏览器缓存是否已清除
- [ ] 是否有拼写错误或语法错误

记住，大多数问题都有解决方案，保持耐心并逐步排查！