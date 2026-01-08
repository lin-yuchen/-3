README - 升捷發展有限公司 网站（静态站）

说明
----
这个目录包含你的静态网站文件，用于部署到 GitHub Pages 或其他静态主机。为了能在线访问并避免使用本地 `file:///` 路径，请把本地桌面上的图片复制到本项目的 `assets/` 子目录中，并确保 HTML 中使用相对路径。

项目结构（当前重要目录）
-------------------------
- index.html 或 `官网.html`（首页）
- details/（详情页）
- assets/
  - assets/logo/  ← 放公司 LOGO 文件（示例文件名：公司LOGO.png）
  - assets/qr/    ← 放页脚二维码图片（示例文件名：qr_wechat_friend.png、qr_whatsapp.png、qr_wechat_official.png、qr_xiaohongshu.png）
  - assets/partners/ ← 合作厂商 LOGO（任意文件名，推荐使用小尺寸 PNG/JPG）

必须文件与建议命名
------------------
为方便自动化和示例，我在 HTML 中引用了以下相对路径。请把对应的桌面图片复制/重命名到这些路径：

- assets/logo/公司LOGO.png
- assets/qr/qr_wechat_friend.png
- assets/qr/qr_whatsapp.png
- assets/qr/qr_wechat_official.png
- assets/qr/qr_xiaohongshu.png

（合作厂商可任意命名，但请放到 `assets/partners/` 下，或者替换 `官网.html` 中的相应 <img> src）

本地测试（Windows PowerShell）
----------------------------
在项目根打开 PowerShell，然后运行：

```powershell
cd C:\Users\Administrator\Desktop\website-project
python -m http.server 8000
```

然后在浏览器打开：http://localhost:8000/ 或 http://localhost:8000/官网.html

如果你使用 Node.js，也可以用：

```powershell
npx http-server -p 8000
```

Git / GitHub 快速指南
--------------------
1. 在 GitHub 创建仓库（例如 `company-site`）。
2. 在本地初始化并推送：

```powershell
cd C:\Users\Administrator\Desktop\website-project
git init
git add .
git commit -m "Initial site commit"
git remote add origin https://github.com/<your-username>/company-site.git
git branch -M main
git push -u origin main
```

3. 在仓库 Settings → Pages 中选择发布源（main 分支 root 或 docs/），等待生效后访问 GitHub Pages 提供的 URL。

注意事项
-------
- 不要把 API 密钥或敏感信息写入前端文件。
- `file:///` 路径在 GitHub Pages 上无效，所以务必把图片复制到 `assets/` 并使用相对路径。
- 若你想让 README 中的占位文件由我自动生成（例如将占位图片写入仓库），请上传图片或允许我创建占位文件。

如果需要，我可以：
- 继续替换 `details/` 下的路径（已检查，无本地 file:/// 引用）。
- 帮你把 `官网.html` 重命名为 `index.html`（推荐），并调整链接。
- 生成 GitHub Actions workflow 自动部署配置。

