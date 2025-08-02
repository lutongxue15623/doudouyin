# 短链接管理系统

一个基于 Vue.js 3 的短链接管理系统，支持链接管理、二维码解析、访问统计等功能。

## 🌟 功能特性

- 🔐 用户登录系统
- 🔗 短链接生成和管理
- 📱 二维码图片解析
- 📊 访问统计和数据分析
- 🎨 现代化响应式界面
- 📱 移动端适配

## 🚀 快速部署

### 方法一：Vercel 部署 (推荐)

1. **注册 Vercel**
   - 访问 https://vercel.com
   - 使用 GitHub 账号登录

2. **导入项目**
   ```bash
   # 将项目推送到 GitHub
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/lutongxue15623/doudouyin.git    
   git push -u origin main
   ```

3. **部署到 Vercel**
   - 在 Vercel 中导入 GitHub 仓库
   - 选择 Vue.js 框架
   - 自动部署完成

### 方法二：Netlify 部署

1. **注册 Netlify**
   - 访问 https://netlify.com
   - 使用 GitHub 账号登录

2. **构建项目**
   ```bash
   npm install
   npm run build
   ```

3. **部署**
   - 将 `dist` 目录拖拽到 Netlify
   - 或连接 GitHub 仓库自动部署

### 方法三：传统服务器部署

1. **构建项目**
   ```bash
   npm install
   npm run build
   ```

2. **上传文件**
   - 将 `dist` 目录内容上传到服务器
   - 配置 Nginx 或 Apache

3. **Nginx 配置示例**
   ```nginx
   server {
       listen 80;
       server_name your-domain.com;
       root /var/www/shortlink-manager;
       index index.html;
       
       location / {
           try_files $uri $uri/ /index.html;
       }
   }
   ```

## 🔧 部署后配置

### 更新短链接域名

部署完成后，需要更新短链接的域名配置：

1. **找到 LinkManagement.vue 文件**
2. **修改 generateShortUrl 方法**：

```javascript
// 将
return `${window.location.origin}/s/${result}`

// 替换为你的域名
return `https://your-domain.com/s/${result}`
```

### 环境变量配置

创建 `.env.production` 文件：

```env
VUE_APP_BASE_URL=https://your-domain.com
VUE_APP_API_URL=https://your-api-domain.com
```

## 📱 使用说明

### 管理员登录
- 用户名：`admin`
- 密码：`admin`

### 功能模块
1. **链接管理**：创建、编辑、删除短链接
2. **副码管理**：管理副码相关功能
3. **活码链接**：动态链接管理

### 短链接访问
- 格式：`https://your-domain.com/s/abc123`
- 自动跳转到目标URL
- 记录访问统计

## 🛠️ 技术栈

- **前端框架**：Vue.js 3
- **路由管理**：Vue Router 4
- **二维码解析**：jsQR
- **样式**：CSS3 + 响应式设计
- **存储**：localStorage

## 📊 访问统计

- 总访问次数统计
- 独立访客统计
- 访问历史记录
- 设备去重统计

## 🔒 安全特性

- 设备ID生成和验证
- 访问记录去重
- 链接状态控制
- 错误处理机制

## 📞 支持

如有问题，请提交 Issue 或联系开发者。

## �� 许可证

MIT License
