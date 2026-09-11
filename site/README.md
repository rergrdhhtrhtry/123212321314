# 一场像素科普冒险 · GitHub Pages 部署包

把 `site/` 整个目录推到 GitHub 仓库根目录，开启 Pages 即可访问。

## 文件结构
```
site/
├── index.html              # 入口（必须叫 index.html）
├── .nojekyll               # 跳过 Jekyll 处理
└── assets/
    ├── bci_brain.png       # 北脑一号关
    ├── haven_station.png   # Haven-1 关
    └── na_battery_car.png  # 钠新电池关
```

## 部署步骤（3 分钟）

### 1. 新建仓库
在 GitHub 新建一个公开仓库，例如 `tech-explorer-game`。

### 2. 推送内容
进入 `site/` 目录执行：
```bash
cd site
git init
git add .
git commit -m "deploy: pixel tech explorer"
git branch -M main
git remote add origin https://github.com/<你的用户名>/tech-explorer-game.git
git push -u origin main
```

### 3. 开启 Pages
- 仓库页 → Settings → Pages
- Source: `Deploy from a branch`
- Branch: `main` / `/ (root)` → Save
- 等待 1~2 分钟，访问 `https://<你的用户名>.github.io/tech-explorer-game/`

## 为什么不是直接 push 整个 `PPT项目/` 文件夹？

| 问题 | 症状 | 解决 |
|---|---|---|
| 入口文件名带中文空格下划线 | Pages 不识别为默认首页 → **整页 404** | 改为 `index.html` |
| 资产文件名含 `:`（Windows 合法 / GitHub 非法） | 图片 push 不上 / 仓库显示缺图 | 清洗为 `bci_brain.png` 等纯英文文件名 |
| 中文 README 在 Pages 主页无影响但 build 警告 | Jekyll 抛 warning | `.nojekyll` 禁用 Jekyll |

## 本地预览
```bash
cd site
python -m http.server 8000
# 浏览器打开 http://localhost:8000
```

## 操作
- 点击 / 空格 / 回车 → 推进对话与关卡
- 答对 +33 EXP / 答错 -1 HP（耗尽自动补满）
- 右上角切弹幕，`M` 键回地图

## 数据来源
MIT Technology Review《2026 十大突破技术》 · 央视《新闻 1+1》 · 新华社 · 中国经济网 · Vast Space 官方
配图为 AI 生成概念图（像素化处理），非实物照片 ｜ Haven-1 发射日期以官方为准