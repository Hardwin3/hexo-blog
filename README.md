# Hexo Blog

个人博客源码仓库，基于 Hexo + NexT 主题。

## 仓库

- 源码仓库：`Hardwin3/hexo-blog`（本仓库）
- 旧部署仓库：`Hardwin3/Hardwin3.github.io`（已弃用，保留备份）

## 部署方式（新）

推送源码到 GitHub，Vercel 自动构建部署。

```bash
# 写完文章后
git add .
git commit -m "添加新文章 xxx"
git push
```

Vercel 配置（`vercel.json`）：
- Install Command: `npm install`
- Build Command: `npm run clean && npm run build`
- Output Directory: `public`

Vercel 域名：`https://hexo-blog-lovat.vercel.app`

## 部署方式（旧，已弃用）

以前使用 `hexo deploy` 将编译产物推送到 `Hardwin3.github.io` 仓库。

```bash
hexo clean
hexo generate
hexo deploy
```

`_config.yml` 中的 deploy 配置保留未删，需要时可随时恢复。

## 目录结构

```
blog-hexo/
├── source/_posts/    # 文章（Markdown）
├── themes/next/      # NexT 主题
├── _config.yml       # Hexo 配置
├── vercel.json       # Vercel 部署配置
└── package.json      # 依赖
```

## 常用命令

```bash
hexo new "文章标题"     # 新建文章
hexo clean              # 清除缓存
hexo generate           # 生成静态文件
hexo server             # 本地预览 (localhost:4000)
```

## 切回旧部署方式

如果需要恢复 `hexo deploy` 方式部署到 `Hardwin3.github.io`：

1. 确保 `_config.yml` 中 deploy 配置存在且正确
2. 安装依赖：`npm install`
3. 执行部署：`hexo clean && hexo generate && hexo deploy`
