# PicSpark - AI驱动的产品设计截图管理与灵感发现平台

![PicSpark Logo](https://via.placeholder.com/200x100?text=PicSpark)

## 🎯 项目介绍

PicSpark 是一个专为产品设计师和UI/UX从业者打造的AI驱动截图管理与灵感发现平台。它能够智能分析、分类和标记设计截图，帮助您快速发现设计趋势、构建个人灵感库，并与团队协作分享设计灵感。

## ✨ 核心功能

### 🖼️ 智能截图管理
- **AI自动标记**：自动识别截图中的UI元素、颜色、字体等设计特征
- **智能分类**：基于内容自动分类（移动端、网页、品牌、插画等）
- **语义搜索**：通过自然语言描述搜索相关设计案例
- **重复检测**：智能识别相似或重复截图

### 🔍 灵感发现引擎
- **趋势分析**：基于上传内容生成设计趋势报告
- **相似推荐**：发现与您收藏相似的优秀设计
- **色彩提取**：自动提取配色方案并生成调色板
- **组件识别**：识别按钮、卡片、导航等UI组件

### 👥 团队协作
- **共享画板**：创建团队灵感库
- **评论系统**：针对设计细节进行讨论
- **版本追踪**：记录设计迭代历程
- **权限管理**：灵活的访问控制

### 📊 分析与报告
- **个人洞察**：分析您的设计偏好和发展轨迹
- **团队报告**：团队协作和设计决策数据
- **趋势预测**：基于行业数据的设计趋势预测

## 🚀 快速开始

### 环境要求
- Node.js 18+
- PostgreSQL 14+
- Redis 6+
- pnpm 8+

### 本地开发

#### 1. 克隆项目
```bash
git clone https://github.com/Tianyu199509/picspark.git
cd picspark
```

#### 2. 安装依赖
```bash
pnpm install
```

#### 3. 环境配置
```bash
# 复制环境变量模板
cp .env.example .env

# 编辑 .env 文件，配置以下关键变量：
# DATABASE_URL="postgresql://username:password@localhost:5432/picspark"
# REDIS_URL="redis://localhost:6379"
# OPENAI_API_KEY="your-openai-key"
# CLERK_SECRET_KEY="your-clerk-key"
```

#### 4. 启动服务
```bash
# 启动所有服务（Web + API + 数据库）
pnpm docker:up

# 或者分别启动
pnpm dev:web    # 启动前端开发服务器
pnpm dev:api    # 启动后端API服务器
```

#### 5. 数据库初始化
```bash
# 运行数据库迁移
pnpm db:migrate

# 生成种子数据（可选）
pnpm db:seed

# 打开数据库管理界面
pnpm db:studio
```

### 访问应用
- **Web应用**: http://localhost:3000
- **API文档**: http://localhost:8000/docs
- **数据库管理**: http://localhost:5555

## 📁 项目结构

```
picspark/
├── apps/
│   ├── web/                    # Next.js前端应用
│   └── api/                    # FastAPI后端服务
├── packages/
│   ├── ui/                     # 共享UI组件库
│   ├── shared/                 # 共享类型和工具
│   └── config/                 # 配置文件
├── docker-compose.yml          # 本地开发环境
├── turbo.json                  # Turborepo配置
└── README.md
```

## 🛠️ 技术栈

### 前端
- **框架**: Next.js 14 (App Router)
- **样式**: Tailwind CSS + shadcn/ui
- **状态管理**: Zustand + React Query
- **上传**: react-dropzone + tus
- **搜索**: Algolia InstantSearch

### 后端
- **框架**: FastAPI (Python)
- **数据库**: PostgreSQL + Prisma ORM
- **缓存**: Redis
- **AI/ML**: OpenAI GPT-4V, CLIP, Scikit-learn
- **任务队列**: Celery + RabbitMQ
- **存储**: AWS S3 (本地开发使用MinIO)

### DevOps
- **容器化**: Docker + Docker Compose
- **CI/CD**: GitHub Actions
- **部署**: Vercel (前端) + Railway (后端)
- **监控**: Sentry + LogRocket

## 🎯 使用场景

### 个人设计师
- **灵感收集**: 浏览网页时一键保存优秀设计
- **项目管理**: 按客户/项目组织设计参考
- **技能提升**: 通过AI分析了解自己的设计风格变化

### 设计团队
- **团队知识库**: 构建团队共享的设计资源库
- **设计评审**: 基于真实案例进行设计决策
- **新人培训**: 快速了解团队设计标准和偏好

### 产品经理
- **竞品分析**: 系统收集和分析竞品设计
- **需求沟通**: 用具体设计案例说明需求
- **趋势跟踪**: 了解行业设计发展趋势

## 🔧 配置详解

### AI服务配置
```env
# OpenAI (必需)
OPENAI_API_KEY=sk-...

# 可选的AI服务
ANTHROPIC_API_KEY=sk-ant-...
GOOGLE_AI_API_KEY=...

# 本地AI模型 (可选)
OLLAMA_API_URL=http://localhost:11434
```

### 存储配置
```env
# 文件存储
STORAGE_TYPE=s3  # s3 | local
S3_BUCKET=your-bucket
S3_REGION=us-east-1
AWS_ACCESS_KEY_ID=...
AWS_SECRET_ACCESS_KEY=...

# CDN配置 (可选)
CDN_URL=https://your-cdn.com
```

### 认证配置
```env
# Clerk (推荐)
CLERK_PUBLISHABLE_KEY=pk_test_...
CLERK_SECRET_KEY=sk_test_...

# 或者使用NextAuth
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your-secret
```

## 📊 性能优化

### 图片处理
- **自动压缩**: 上传时自动优化图片大小
- **格式转换**: 支持WebP/AVIF现代格式
- **响应式**: 根据设备提供合适尺寸
- **懒加载**: 虚拟滚动处理大量图片

### 搜索优化
- **全文搜索**: PostgreSQL全文检索 + 向量搜索
- **缓存策略**: Redis缓存热门搜索结果
- **分页加载**: 无限滚动优化用户体验

## 🧪 开发指南

### 代码规范
- **TypeScript**: 严格模式，完整类型定义
- **ESLint**: Airbnb规范 + 自定义规则
- **Prettier**: 统一代码格式
- **Husky**: Git hooks确保代码质量

### 测试策略
```bash
# 运行测试
pnpm test          # 所有测试
pnpm test:web      # 前端测试
pnpm test:api      # 后端测试

# 端到端测试
pnpm test:e2e
```

### 贡献指南
1. Fork 项目
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

## 🚀 部署指南

### 生产环境部署

#### Vercel (前端)
[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/Tianyu199509/picspark)

#### Railway (后端)
[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/picspark)

#### Docker部署
```bash
# 构建生产镜像
docker build -t picspark .

# 运行容器
docker run -p 3000:3000 --env-file .env picspark
```

## 📈 路线图

### 即将推出 (v1.1)
- [ ] Figma插件集成
- [ ] Chrome扩展程序
- [ ] 团队协作实时同步
- [ ] 设计系统管理

### 未来规划 (v2.0)
- [ ] 移动端应用 (React Native)
- [ ] 视频录制和分析
- [ ] AI设计助手
- [ ] 社区功能

## 🤝 社区支持

- **问题反馈**: [GitHub Issues](https://github.com/Tianyu199509/picspark/issues)
- **功能请求**: [GitHub Discussions](https://github.com/Tianyu199509/picspark/discussions)
- **实时聊天**: [Discord社区](https://discord.gg/picspark)
- **文档**: [官方文档](https://docs.picspark.app)

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 🙏 致谢

- 感谢所有为开源社区做出贡献的开发者
- 特别感谢 [shadcn/ui](https://ui.shadcn.com/) 提供的优秀组件库
- 感谢 [Vercel](https://vercel.com) 和 [Railway](https://railway.app) 提供的免费部署服务

---

**⭐ 如果这个项目对您有帮助，请给个星标支持一下！**