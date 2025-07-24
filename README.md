# PicSpark - AI驱动的设计灵感平台

一个AI驱动的产品截图管理和分析平台，支持自动标签生成、产品分析和图片分析功能。

## 🚀 快速开始

### 前置要求
- Node.js >= 18.0.0
- pnpm >= 8.0.0
- PostgreSQL >= 14

### 安装依赖
```bash
pnpm install:all
```

### 环境配置
```bash
cp .env.example .env
# 编辑 .env 文件配置数据库和API密钥
```

### 数据库初始化
```bash
pnpm db:push
pnpm db:seed
```

### 启动开发服务器
```bash
pnpm dev
```

## 📋 功能特性

### 核心功能
- **AI图片分析**: 自动生成标签、描述和设计分析
- **产品管理**: 产品信息录入、编辑和管理
- **截图管理**: 上传、分类和搜索截图
- **智能搜索**: 基于AI标签和内容的智能搜索
- **团队协作**: 多人协作管理设计资源

### 技术特性
- **前端**: Vue 3 + TypeScript + Vite
- **后端**: Fastify + Prisma + PostgreSQL
- **AI集成**: 支持多种AI模型(OpenAI、Claude等)
- **响应式设计**: 支持桌面和移动设备
- **国际化**: 支持中英文切换

## 🏗️ 技术架构

### 前端技术栈
- **框架**: Vue 3.4 + Composition API
- **构建工具**: Vite 5
- **状态管理**: Pinia
- **路由**: Vue Router 4
- **UI框架**: Bulma + 自定义组件
- **CSS预处理器**: Sass
- **HTTP客户端**: Axios
- **图标**: Lucide React

### 后端技术栈
- **运行时**: Node.js 18+
- **框架**: Fastify 4
- **数据库**: PostgreSQL 14
- **ORM**: Prisma 5
- **认证**: JWT
- **文件上传**: Multer
- **AI集成**: OpenAI API、Claude API
- **图片处理**: Sharp

### 部署架构
- **容器化**: Docker + Docker Compose
- **反向代理**: Nginx
- **云服务**: 支持腾讯云、阿里云等

## 📁 项目结构

```
picspark/
├── apps/
│   ├── api/                 # 后端API服务
│   │   ├── src/
│   │   │   ├── routes/      # API路由
│   │   │   ├── services/    # 业务逻辑
│   │   │   ├── models/      # 数据模型
│   │   │   └── utils/       # 工具函数
│   │   └── prisma/          # 数据库schema和迁移
│   └── web/                 # 前端Web应用
│       ├── src/
│       │   ├── components/  # Vue组件
│       │   ├── views/       # 页面组件
│       │   ├── stores/      # Pinia状态管理
│       │   ├── router/      # 路由配置
│       │   └── utils/       # 工具函数
│       └── public/          # 静态资源
├── deploy/                  # 部署配置
├── docs/                    # 项目文档
└── shared/                  # 共享类型定义
```

## 🎯 使用指南

### 管理员功能
1. **产品管理**: 添加、编辑和删除产品信息
2. **图片管理**: 批量上传和管理产品截图
3. **AI分析**: 对产品图片进行AI分析
4. **用户管理**: 管理用户权限和角色

### 用户功能
1. **浏览产品**: 查看所有产品及其截图
2. **搜索筛选**: 使用标签、关键词搜索产品
3. **收藏功能**: 收藏感兴趣的产品
4. **分享功能**: 分享产品到社交媒体

## 🔧 开发指南

### 代码规范
- 使用ESLint进行代码检查
- 使用Prettier进行代码格式化
- 遵循Vue 3风格指南

### 分支管理
- `main`: 生产分支
- `develop`: 开发分支
- `feature/*`: 功能分支
- `hotfix/*`: 紧急修复分支

### 提交规范
- `feat`: 新功能
- `fix`: 修复bug
- `docs`: 文档更新
- `style`: 代码格式调整
- `refactor`: 代码重构
- `test`: 测试相关
- `chore`: 构建过程或辅助工具的变动

## 🚀 部署

### Docker部署
```bash
# 构建镜像
docker-compose build

# 启动服务
docker-compose up -d
```

### 手动部署
1. 安装Node.js和PostgreSQL
2. 克隆代码
3. 安装依赖
4. 配置环境变量
5. 初始化数据库
6. 启动服务

## 🤝 贡献指南

1. Fork本项目
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 创建Pull Request

## 📄 许可证

本项目采用MIT许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 🙋‍♂️ 联系我们

- 邮箱: contact@picspark.com
- 微信: PicSpark官方
- QQ群: 123456789

---

**PicSpark - 让AI为你的设计灵感加速！**