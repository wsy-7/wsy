# 乙酰水杨酸AR虚仿实验教学平台

化学国家级实验教学示范中心（吉林大学）· 虚实融合数智化教学平台

## 目录结构

```
├── index.html          # 主页面（入口文件）
├── 照片/               # 图片资源（二维码、视频封面等）
├── 视频/               # 视频文件
├── 模型/               # 3D 分子模型 (.glb)
└── 参考文献/           # PDF 文献
```

## 本地使用

1. 直接用浏览器打开 `index.html`
2. 或使用本地服务器（推荐，避免 CORS 限制）：
   ```bash
   # Python 3
   python -m http.server 8080
   
   # Node.js (需安装 npx)
   npx serve .
   ```
3. 访问 http://localhost:8080

## 部署到 GitHub Pages

1. 在 GitHub 创建仓库，上传本项目所有文件（保持目录结构）
2. 仓库设置 → Pages → Source 选择 `main` 分支，根目录
3. 访问 `https://你的用户名.github.io/仓库名/` 即可

**注意**：GitHub Pages 使用相对路径时，照片、视频、模型、PDF 会正常加载，一般无需额外配置。

## 使用 GitHub 直链（jsDelivr CDN）

若需通过 jsDelivr 加速或作为直链使用，请修改 `index.html` 顶部的配置：

```html
<script>
  // 将 '' 改为你的 jsDelivr 地址，格式如下：
  window.RESOURCE_BASE = 'https://cdn.jsdelivr.net/gh/你的用户名/仓库名@main/';
</script>
```

**直链格式说明**：
- jsDelivr：`https://cdn.jsdelivr.net/gh/用户名/仓库名@分支/`
- Raw：`https://raw.githubusercontent.com/用户名/仓库名/分支/`

示例：仓库 `my-repo`，用户 `john`，分支 `main`：
```
https://cdn.jsdelivr.net/gh/john/my-repo@main/
```

## 资源直链示例

部署后，各资源直链格式为：

| 类型 | 路径 | 直链示例 |
|------|------|----------|
| 二维码 | 照片/乙酰水杨酸.glb.png | `{BASE}照片/乙酰水杨酸.glb.png` |
| 视频封面 | 照片/阿司匹林.jpg | `{BASE}照片/阿司匹林.jpg` |
| 视频 | 视频/阿司匹林.mp4 | `{BASE}视频/阿司匹林.mp4` |
| 3D模型 | 模型/水杨酸.glb | `{BASE}模型/水杨酸.glb` |
| PDF | 参考文献/xxx.pdf | `{BASE}参考文献/xxx.pdf` |

将 `{BASE}` 替换为你的 jsDelivr 或 raw 地址即可。
