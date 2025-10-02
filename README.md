# WEPhoneShop.es - 数据分析与战略可视化

这是一个静态HTML网站项目，展示WEPhoneShop.es的数据分析与战略可视化内容。

## 项目结构

```
wephone/
├── 01.html          # 主页面文件
├── README.md        # 项目说明文档
├── netlify.toml     # Netlify部署配置
├── vercel.json      # Vercel部署配置
└── .github/
    └── workflows/
        └── deploy.yml   # GitHub Pages自动部署配置
```

## 技术栈

- HTML5
- Tailwind CSS (通过CDN)
- Chart.js (数据可视化)
- Font Awesome (图标)
- Google Fonts (字体)

## 本地预览

### 方法1：使用Python
```bash
cd wephone
python -m http.server 8080
```
然后访问 http://localhost:8080/01.html

### 方法2：使用Node.js
```bash
cd wephone
npx http-server . -p 8080 -o
```

### 方法3：使用Live Server (VS Code扩展)
右键点击 `01.html` 文件，选择 "Open with Live Server"

## 部署选项

### 1. Netlify 部署

#### 方法A：拖拽部署（最简单）
1. 访问 [Netlify](https://www.netlify.com/)
2. 注册/登录账户
3. 将整个 `wephone` 文件夹拖拽到 Netlify 的部署区域
4. 等待部署完成，获得免费的 `.netlify.app` 域名

#### 方法B：Git部署
1. 将项目推送到GitHub仓库
2. 在Netlify中连接GitHub仓库
3. 设置构建配置：
   - Build command: 留空
   - Publish directory: `/`
4. 部署完成后可以设置自定义域名

### 2. Vercel 部署

#### 方法A：CLI部署
```bash
npm i -g vercel
cd wephone
vercel
```

#### 方法B：Git部署
1. 将项目推送到GitHub仓库
2. 访问 [Vercel](https://vercel.com/)
3. 导入GitHub仓库
4. 设置配置：
   - Framework Preset: Other
   - Root Directory: `/`
   - Build Command: 留空
   - Output Directory: `/`

### 3. GitHub Pages 部署

1. 将项目推送到GitHub仓库
2. 在仓库设置中启用GitHub Pages
3. 选择源分支（通常是main或gh-pages）
4. 使用提供的GitHub Actions工作流自动部署

### 4. 其他免费静态托管服务

#### Firebase Hosting
```bash
npm install -g firebase-tools
firebase login
firebase init hosting
firebase deploy
```

#### Surge.sh
```bash
npm install -g surge
cd wephone
surge
```

#### Cloudflare Pages
1. 访问 [Cloudflare Pages](https://pages.cloudflare.com/)
2. 连接GitHub仓库
3. 设置构建配置（与Vercel类似）

## 自定义域名

大多数托管服务都支持自定义域名：

1. 在托管平台的域名设置中添加你的域名
2. 在域名注册商处设置DNS记录：
   - 添加CNAME记录指向托管平台提供的地址
   - 或添加A记录指向托管平台的IP地址

## 性能优化建议

1. **图片优化**：如果添加图片，使用WebP格式并压缩
2. **CDN缓存**：大多数托管服务自动提供CDN
3. **GZIP压缩**：现代托管服务默认启用
4. **HTTP/2**：选择支持HTTP/2的托管服务

## 监控和分析

建议添加以下服务：

- **Google Analytics**：网站访问统计
- **Google Search Console**：SEO监控
- **Hotjar**：用户行为分析

## 维护和更新

1. 定期检查外部CDN链接的可用性
2. 更新Chart.js等依赖库的版本
3. 监控网站性能和加载速度
4. 根据用户反馈优化内容和交互

## 技术支持

如果在部署过程中遇到问题，可以参考各平台的官方文档：

- [Netlify文档](https://docs.netlify.com/)
- [Vercel文档](https://vercel.com/docs)
- [GitHub Pages文档](https://docs.github.com/en/pages)
- [Firebase Hosting文档](https://firebase.google.com/docs/hosting)

## 许可证

本项目仅用于展示目的。请确保遵守所使用的第三方库和服务的许可证条款。