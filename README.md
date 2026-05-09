# ☁️ 云盘

基于 GitHub Pages 的免费个人云盘，所有人可访问、下载，管理员密码登录后可上传管理。

## ✨ 特点

- 🌐 **公开访问** — 任何人打开即可浏览、下载
- 🔒 **密码管理** — 管理员输入密码 + Token 后才能上传/删除
- 📤 拖拽上传 / 点击上传
- 📁 文件夹层级管理
- 👀 预览图片、视频、音频、PDF、代码、文本
- 🔍 实时搜索 / 分类筛选
- 📱 响应式暗色主题
- 💰 完全免费（GitHub Pages + GitHub API）

## 🚀 部署

### 1. 创建仓库

GitHub 新建仓库（如 `my-drive`），**建议 Public**。

### 2. 修改配置

编辑 `index.html` 中的 `CONFIG` 对象：

```javascript
const CONFIG = {
  owner: '你的GitHub用户名',
  repo:  'my-drive',
  branch:'main',
  folder: 'files',           // 文件存放目录
  adminPassword: '改成你的密码'  // 管理登录密码
};
```

### 3. 推送代码

```bash
git add index.html README.md
git commit -m "init cloud drive"
git push origin main
```

### 4. 开启 Pages

**Settings → Pages** → Source: `Deploy from a branch` → Branch: `main` / `/(root)` → Save

### 5. 访问

打开 `https://你的用户名.github.io/my-drive/`

## 🔐 管理模式

1. 点击右上角 **🔒 管理**
2. 输入管理密码（CONFIG 中设置的）
3. 输入 GitHub Token（需要 `repo` 权限）
4. 开启后可上传、重命名、删除文件

**安全说明：**
- 密码和 Token 仅存在浏览器内存中，页面刷新即丢失
- 不会上传到任何第三方
- 建议仓库设为 private（GitHub Pro 才支持 private Pages）

## 📝 限制

- 单文件 ≤ 100MB（GitHub 限制）
- 仓库建议 ≤ 1GB
- API 速率限制：5000 次/小时（认证后）

## License

MIT
