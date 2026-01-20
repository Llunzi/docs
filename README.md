# 产品使用说明文档

这是一个基于 MkDocs 和 Material 主题的产品使用说明文档项目，支持菜单管理和 Drone 自动化部署。

## 功能特点

- 📚 **完整的文档结构**：包含快速开始、功能说明、常见问题等模块
- 🎨 **美观的界面**：使用 Material 主题，支持深色模式和搜索功能
- 📱 **响应式设计**：适配不同屏幕尺寸，支持手机和平板
- 🔍 **强大的搜索**：支持全文搜索和搜索建议
- 🚀 **自动化部署**：使用 Drone CI/CD 自动构建和部署到 GitHub Pages
- 📝 **版本控制**：通过 Git 管理文档版本，支持协作编辑

## 项目结构

```
product-manual/
├── docs/                # 所有文档统一存放目录
│   ├── index.md         # 文档首页
│   ├── 快速开始/        # 模块1：快速开始
│   │   ├── 安装.md
│   │   └── 首次使用.md
│   └── 功能说明/        # 模块2：功能说明
│       ├── 核心功能.md
│       └── 高级配置.md
│   ├── faq.md           # 常见问题
│   └── stylesheets/     # 自定义样式
├── mkdocs.yml           # MkDocs配置（含菜单、主题）
├── .drone.yml           # Drone CI/CD配置（部署用）
└── README.md            # 项目说明
```

## 快速开始

### 1. 安装依赖

```bash
pip install mkdocs mkdocs-material
```

### 2. 本地预览

```bash
mkdocs serve

python3 -m mkdocs serve
```

浏览器访问 `http://127.0.0.1:8000`，修改文档或菜单后，页面会自动刷新。

### 3. 构建静态文件

```bash
mkdocs build
```

构建后的静态文件会生成在 `site` 目录。

### 4. 部署到 GitHub Pages

```bash
mkdocs gh-deploy
```

## 菜单管理

菜单结构在 `mkdocs.yml` 文件中配置，与文档目录结构一一对应：

```yaml
nav:
  - 首页: index.md
  - 快速开始:
    - 安装步骤: 快速开始/安装.md
    - 首次使用: 快速开始/首次使用.md
  - 功能说明:
    - 核心功能: 功能说明/核心功能.md
    - 高级配置: 功能说明/高级配置.md
  - 常见问题: faq.md
```

## Drone 自动化部署

### 1. 配置 Drone

- 部署 Drone Server 并完成 GitHub OAuth 授权
- 在 Drone 中激活仓库并配置 `GITHUB_TOKEN` 秘钥（需要 `repo` 和 `pages` 权限）

### 2. 触发部署

- 将修改推送到 `main` 分支
- Drone 会自动触发构建、部署和打标签

## 贡献指南

1. 创建 `dev` 分支进行编辑
2. 修改文档或菜单配置
3. 提交 PR 并等待审核
4. 审核通过后合并到 `main` 分支

## 许可证

MIT
