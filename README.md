# 迷你世界文件加解密工具

一个基于Web的文件加解密工具，专为迷你世界游戏文件设计，支持所有文件格式的加密和解密操作。本项目可加解密大于等于0.40，小于1.0的迷你世界版本

## ✨ 功能特性

- 🔐 **文件加密/解密** - 支持单文件和批量文件处理
- 📁 **文件夹处理** - 支持整个文件夹的拖拽上传和处理
- 🎨 **智能主题** - 根据时间自动切换明暗主题（20:00-8:00为暗色主题）
- 📦 **批量下载** - 处理完成后可打包下载为ZIP文件
- 🚀 **实时进度** - 显示文件处理进度条
- 💾 **文件大小限制** - 单文件最大100MB，总文件大小最大500MB
- 🎯 **拖拽上传** - 支持拖拽文件和文件夹到页面进行上传

## 🛠️ 技术栈

- **前端框架**: React 18 + TypeScript
- **构建工具**: Vite
- **样式框架**: Tailwind CSS
- **图标库**: Lucide React
- **文件处理**: JSZip
- **压缩算法**: Web Streams API (CompressionStream/DecompressionStream)

## 🚀 快速开始

### 环境要求

- Node.js >= 16.0.0
- npm >= 7.0.0

### 安装依赖

```bash
npm install
```

### 开发模式

```bash
npm run dev
```

### 构建生产版本

```bash
npm run build
```

### 预览生产版本

```bash
npm run preview
```

## 📖 使用说明

1. **选择模式**: 点击"加密"或"解密"按钮选择处理模式
2. **上传文件**: 
   - 拖拽文件/文件夹到上传区域
   - 或点击"选择文件"/"选择文件夹"按钮
3. **开始处理**: 点击"开始处理"按钮
4. **下载结果**: 
   - 单文件：点击对应文件的"下载"按钮
   - 多文件：点击"下载所有文件(ZIP)"按钮

## 🔧 核心算法

### 加密流程
1. 使用 Deflate 算法压缩原始文件
2. 使用 XOR 密钥对压缩数据进行加密
3. 在加密数据前添加8字节头部

### 解密流程
1. 移除文件前8字节头部
2. 使用 XOR 密钥解密数据
3. 使用 Deflate 算法解压缩数据

### 密钥信息
```typescript
const KEY = new Uint8Array([0xd6, 0x02, 0x08, 0x00, 0xf4, 0xfe, 0xff, 0x3f, 0x01, 0x00, 0x00, 0x00, 0xd0, 0xca, 0x01, 0x00]);
```

## 📁 项目结构

```
/
项目录目
├── src/                          # 源码根目录
│   ├── components/               # 可复用 React 组件
│   ├── lib/                      # 通用工具库
│   │   └── fileProcessor.ts      # 文件处理逻辑
│   ├── App.tsx                   # 根组件
│   ├── index.css                 # 全局样式（Tailwind）
│   ├── main.tsx                  # 应用入口
│   └── vite-env.d.ts             # Vite 环境类型声明
├── .gitignore
├── eslint.config.js              # ESLint 配置（9.x 扁平化）
├── index.html                    # Vite 入口 HTML
├── LICENSE
├── package.json
├── package-lock.json
├── postcss.config.js             # PostCSS 配置（Tailwind）
├── README.md
├── tailwind.config.js            # Tailwind 配置
├── tsconfig.json                 # TypeScript 主配置
├── tsconfig.app.json             # 应用代码 TS 配置
├── tsconfig.node.json            # Node 环境 TS 配置
└── vite.config.ts                # Vite 配置
```

## 🎨 界面特性

- **响应式设计**: 适配各种屏幕尺寸
- **暗色主题**: 20:00-8:00自动启用暗色主题
- **进度指示**: 实时显示文件处理进度
- **错误处理**: 友好的错误提示和处理
- **文件预览**: 显示选中文件的详细信息

## ⚠️ 注意事项

- 单个文件大小不能超过100MB
- 总文件大小不能超过500MB
- 建议在现代浏览器中使用（支持Web Streams API）
- 处理大文件时请耐心等待

## 📄 开源协议

本项目采用 [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0) 开源协议。

## 🔗 相关链接

- **官方网站**: [https://www.scmgzs.top/](https://www.scmgzs.top/)
- **官方QQ群**: 1012670256

## 👨‍💻 作者信息

- **作者**: 是史三问呀
- **QQ**: 2196634956

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request 来帮助改进项目！

## 📝 更新日志

### v1.0.0
- 初始版本发布
- 支持文件加密/解密功能
- 支持批量文件处理
- 支持文件夹拖拽上传
- 自动主题切换功能

---

## 📄 版权与许可

本作品采用 [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0) 开源协议。

版权所有 © 2025 创梦星际

在遵守 Apache 2.0 协议的前提下，您可以自由地使用、复制、修改和分发本作品。  
有关许可的详细信息，请访问 [Apache License 2.0 全文](http://www.apache.org/licenses/LICENSE-2.0)。

如果这个项目对您有帮助，请给个 ⭐ Star 支持一下！
