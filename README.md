<p align="center">
  <img src="https://via.placeholder.com/120x120?text=✨" alt="PicSpark" width="120">
</p>

<p align="center">
  <b>让产品设计更智能，让灵感触手可及</b><br>
  <i>AI分析 • 智能标签 • 社区互动</i>
</p>

<p align="center">
  <a href="#快速开始">快速开始</a> •
  <a href="#功能特性">功能特性</a> •
  <a href="#技术架构">技术架构</a> •
  <a href="#开发指南">开发指南</a>
</p>

## 产品定位

一个专注于**UI/UX设计灵感**的智能平台，通过AI分析帮助设计师和产品经理快速获取设计洞察。

**核心价值**：
- 🎨 **设计灵感聚合** - 精选移动端UI截图，智能分类展示
- 🤖 **AI设计分析** - 自动识别设计模式、交互方式、视觉风格
- 🔍 **智能搜索** - OCR文字识别，支持设计元素精准搜索
- 💬 **设计社区** - 设计师交流、收藏、评论互动平台

## 功能特性

### 🎨 智能设计展示
- **瀑布流布局** - 响应式瀑布流，完美展示各种尺寸的UI截图
- **智能预览** - 点击放大，支持缩放、旋转，流畅的交互体验
- **AI设计分析** - 自动识别设计模式、色彩搭配、布局结构
- **相似推荐** - 基于视觉相似度推荐相关设计

### 🔍 精准搜索体验
- **OCR文字识别** - 截图中的文字内容可被搜索和索引
- **多维度筛选** - 按设计风格、颜色、组件类型、行业分类
- **实时搜索** - 输入即搜索，无需等待，流畅体验
- **标签系统** - AI自动标签 + 用户自定义标签

### 💫 社区互动
- **一键收藏** - 快速收藏喜欢的设计，建立个人灵感库
- **设计评论** - 设计师之间的专业交流和反馈
- **分享功能** - 支持链接分享、图片导出、设计对比
- **用户主页** - 展示个人收藏、发布内容、设计偏好

## 技术架构

- **前端**: Vue 3 + TypeScript + Tailwind CSS
- **后端**: Node.js + Fastify + Prisma + SQLite
- **AI分析**: 集成OpenAI GPT-4、Claude等AI模型
- **OCR**: Tesseract.js 文字识别
- **部署**: Docker容器化部署

## 快速开始

### 环境要求
- Node.js 18+
- pnpm 包管理器
- Docker (可选)

### 本地开发

1. 克隆项目
```bash
git clone https://github.com/Tianyu199509/picspark.git
cd picspark
```

2. 安装依赖
```bash
pnpm install
```

3. 配置环境变量
```bash
cp .env.example .env
# 编辑 .env 文件，配置必要的环境变量
```

4. 启动数据库和开发服务器
```bash
# 启动数据库容器（可选）
pnpm docker:up

# 数据库迁移
pnpm db:migrate

# 启动开发服务器
pnpm dev
```

5. 访问应用
- 前端: http://localhost:5173
- 后端API: http://localhost:3000
- 数据库管理: http://localhost:5555 (Prisma Studio)

### Docker部署

```bash
# 构建镜像
docker-compose build

# 启动服务
docker-compose up -d
```

## 开发指南

### 项目结构
```
picspark/
├── apps/
│   ├── web/          # 前端应用 (Vue 3)
│   └── api/          # 后端API (Fastify)
├── packages/         # 共享包
├── docs/            # 文档
└── deploy/          # 部署配置
```

### 常用命令

```bash
# 开发模式
pnpm dev              # 同时启动前端和后端
pnpm dev:web          # 仅启动前端
pnpm dev:api          # 仅启动后端

# 构建
pnpm build            # 构建所有应用
pnpm build:web        # 仅构建前端
pnpm build:api        # 仅构建后端

# 数据库操作
pnpm db:migrate       # 运行数据库迁移
pnpm db:generate      # 生成Prisma客户端
pnpm db:seed          # 填充测试数据
pnpm db:studio        # 启动数据库管理界面

# 代码质量
pnpm lint             # 代码检查
pnpm lint:fix         # 自动修复代码格式
pnpm type-check       # TypeScript类型检查
```

## 贡献指南

1. Fork 本项目
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 创建 Pull Request

## 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。