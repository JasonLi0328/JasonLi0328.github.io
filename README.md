# 我的个人主页

基于 [Maggie Thompson](https://www.maggie-thompson.com) 布局风格的个人主页，纯 HTML + CSS 实现，无需任何构建工具。

---

## 📁 文件结构

```
/
├── index.html       ← 网站全部内容（HTML + CSS + JS 在一个文件里）
├── photo.jpg        ← 放你的照片（替换占位绿色方块）
└── README.md        ← 本说明
```

---

## ✏️ 如何修改内容

直接用任何文本编辑器（VS Code、记事本等）打开 `index.html`，搜索以下关键词替换：

| 搜索这个         | 替换成               |
|------------------|----------------------|
| `你的姓名`        | 你的真实姓名          |
| `你的邮箱@example.com` | 你的邮箱         |
| `你的LinkedIn`    | 你的 LinkedIn 用户名  |
| `[公司名]`        | 各段落中的公司名       |
| `[职位名称]`      | 对应职位名            |

### 替换照片

1. 把你的照片命名为 `photo.jpg` 放在同一目录
2. 在 `index.html` 中找到以下注释：
   ```html
   <!-- 换成真实照片后：
   <img src="photo.jpg" alt="你的姓名" />
   -->
   ```
3. 删掉 `<div class="photo-placeholder"></div>` 那行
4. 取消注释 `<img>` 标签

---

## 🚀 部署到 GitHub Pages

### 第一步：创建 GitHub 仓库

1. 登录 [github.com](https://github.com)
2. 点击右上角 **+** → **New repository**
3. 仓库名填 `你的用户名.github.io`（例如 `zhangsan.github.io`）
4. 选 **Public**，点击 **Create repository**

### 第二步：上传文件

**方法 A（网页上传，最简单）：**
1. 进入刚创建的仓库
2. 点击 **Add file** → **Upload files**
3. 把 `index.html`（和 `photo.jpg`）拖拽上传
4. 点击 **Commit changes**

**方法 B（命令行）：**
```bash
git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/你的用户名/你的用户名.github.io.git
git push -u origin main
```

### 第三步：开启 GitHub Pages

1. 进入仓库 → **Settings** → 左侧菜单 **Pages**
2. Source 选 **Deploy from a branch**
3. Branch 选 **main**，目录选 **/ (root)**
4. 点击 **Save**

⏱ 等 1-3 分钟后，访问 `https://你的用户名.github.io` 即可看到网站。

---

## 🌐 绑定自定义域名

### 在 GitHub 设置域名

1. 仓库 → **Settings** → **Pages**
2. 在 **Custom domain** 输入你的域名（如 `www.yourname.com`）
3. 点击 **Save**
4. 勾选 **Enforce HTTPS**（建议）

这会在仓库根目录自动创建一个 `CNAME` 文件。

### 在域名注册商配置 DNS

根据你想使用的格式选一种：

**如果用 www 子域名（推荐：`www.yourname.com`）：**

| 类型  | 主机记录 | 记录值                      |
|-------|----------|-----------------------------|
| CNAME | www      | 你的用户名.github.io         |

**如果用裸域名（`yourname.com`）：**

| 类型 | 主机记录 | 记录值           |
|------|----------|------------------|
| A    | @        | 185.199.108.153  |
| A    | @        | 185.199.109.153  |
| A    | @        | 185.199.110.153  |
| A    | @        | 185.199.111.153  |

⏱ DNS 生效通常需要 10 分钟到 48 小时。

### 推荐域名注册商

- **Namecheap**（便宜、界面友好）
- **Cloudflare**（免费 DNS 管理、自带 CDN）
- **阿里云/腾讯云**（如果偏好国内服务）

---

## 🎨 修改主题色

在 `index.html` 顶部 `<style>` 里找到 `:root` 变量块：

```css
:root {
  --bg:      #f4f3ee;   /* 页面背景 */
  --green:   #6b8f5e;   /* 主题色（按钮、链接、边框）*/
  --text:    #2c2c2c;   /* 正文颜色 */
}
```

改这几个颜色值即可全站换色。
