# Word Quest · KET 词汇大冒险

这是可直接部署到 Vercel 的纯静态版本，不依赖数据库、服务器或 API 密钥。

本增强版内置 300 个 KET（A2 Key）核心词，依据剑桥 2025 年更新的官方 A2 Key Vocabulary List，并参考当前官方数字样题及教师手册所覆盖的生活、学校、出行、购物、健康、天气等高频场景筛选。剑桥不公开真实考试逐词频次，因此“高频”表示官方范围内的核心备考优先级，并非官方公布的考试词频排名。

## 目录结构

```text
ket-word-game-vercel/
├── index.html          页面入口
├── styles.css          界面样式与响应式布局
├── app.js              游戏逻辑、发音、词库和本地存储
├── package.json        项目信息与本地预览命令
├── vercel.json         Vercel 配置
├── README.md           部署与目录说明
└── assets/
    ├── favicon.svg     网站图标
    └── og.png          分享封面
```

## Vercel 部署

1. 将整个文件夹提交到 GitHub。
2. 在 Vercel 选择 **Add New → Project** 并导入仓库。
3. Framework Preset 选择 **Other**。
4. Framework Preset 选择 **Other**。
5. Build Command 可使用 `npm run build`。
6. Output Directory 填写 `.`，然后点击 Deploy。

项目中的 `vercel.json` 已明确设置 `"outputDirectory": "."`，它会覆盖 Vercel 控制台中旧的 `public` 设置。

也可以在本目录运行 `npx vercel`。

## 数据说明

- 自定义词库、掌握度和最佳连胜保存在浏览器 `localStorage` 中。
- 不同设备的数据互不同步。
- 发音使用浏览器 Web Speech API，声音由设备决定。
- 词库每行格式：`英文, 中文`，至少 4 个有效单词。
