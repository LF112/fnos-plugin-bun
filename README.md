<div align="center">

<img src="ICON_256.PNG" alt="fnos-plugin-bun Logo" width="128" height="128">

# fnos-plugin-bun

**🚀 飞牛OS的Bun运行时环境插件**

[![Version](https://img.shields.io/badge/version-1.3.6-blue.svg)](https://github.com/LF112/fnos-plugin-bun)
[![Bun](https://img.shields.io/badge/Bun-v1.3.6-black.svg)](https://bun.sh)
[![FnOS](https://img.shields.io/badge/FnOS-Plugin-orange.svg)](https://www.fnnas.com)

</div>

---

## 📖 项目简介

fnos-plugin-bun 是为**飞牛OS**（FnOS）打造的 Bun 运行时环境支持插件。Bun 是一款快速、可渐进式采用的一体化 JavaScript、TypeScript 和 JSX 工具包，可作为 Node.js 的高性能替代方案。

### ✨ 特性

- 🔥 **高性能运行时** - 基于 JavaScriptCore 引擎，启动速度比 Node.js 快 4 倍
- 📦 **内置工具链** - 集成打包器、测试运行器、包管理器，无需额外配置
- ⚡ **快速安装** - 智能安装程序支持在线/离线安装，自动检测系统架构
- 🔄 **Node.js 兼容** - 致力于实现 100% 的 Node.js API 兼容性
- 🎯 **开箱即用** - 自动配置环境变量，无需手动设置

## 🎯 系统要求

- **操作系统**: FnOS (飞牛OS)
- **架构支持**: 
  - ✅ x86_64 (AMD64) - 支持离线/在线安装
  - ✅ ARM64 (aarch64) - 仅支持在线安装
- **依赖**: unzip (在线安装时需要)

## 📦 安装方式

### 方式一：离线安装 (推荐)

适用于内网环境或网络受限场景，预装 Bun v1.3.6 baseline 版本（仅包含 x86_64 架构离线包）。

1. 在飞牛OS应用商店中找到 **Bun**
2. 选择 **离线安装**
3. 等待安装完成

### 方式二：在线安装

支持所有架构，自动下载最新版本。

1. 在飞牛OS应用商店中找到 **Bun**
2. 选择 **在线安装**
3. (可选) 配置 GitHub 镜像地址加速下载
4. 等待下载和安装完成

> 💡 **提示**: 在线安装时建议配置代理或使用 GitHub 镜像以提高下载速度。

## 🚀 使用指南

### 在飞牛应用中声明依赖

如果您的飞牛应用需要使用 Bun 环境，请在 `manifest` 文件中声明依赖：

```bash
install_dep_apps=fnos-plugin-bun
```

### 在脚本中使用 Bun

在您的应用脚本 (`cmd/*`) 中添加以下内容：

```bash
export PATH=/var/apps/fnos-plugin-bun/target/bin:$PATH
```

之后即可使用 Bun 的所有功能：

```bash
# 运行 JavaScript/TypeScript 文件
bun run index.ts

# 安装依赖
bun install

# 运行测试
bun test

# 打包应用
bun build ./index.ts --outdir ./dist
```

## 📂 项目结构

```
fnos-plugin-bun/
├── app/                       # 应用资源目录
│   └── bun-linux-x64-baseline.zip  # 离线安装包
├── cmd/                       # 命令脚本
│   ├── main                   # 主程序入口
│   ├── install_init           # 安装初始化
│   ├── install_callback       # 安装回调
│   ├── upgrade_init           # 升级初始化
│   ├── upgrade_callback       # 升级回调
│   ├── uninstall_init         # 卸载初始化
│   ├── uninstall_callback     # 卸载回调
│   ├── config_init            # 配置初始化
│   └── config_callback        # 配置回调
├── config/                    # 配置目录
│   ├── privilege              # 权限配置
│   └── resource               # 资源配置
├── wizard/                    # 安装向导
│   └── install                # 安装配置界面
├── manifest                   # 应用清单文件
├── ICON.PNG                   # 应用图标
├── ICON_256.PNG               # 应用图标 (256x256)
└── README.md                  # 项目说明文档
```

## 🔧 技术细节

### 自动架构检测

安装脚本会自动检测系统架构和CPU特性：

- 检测是否支持 AVX2 指令集
- 自动选择 baseline 或优化版本
- 支持 musl libc (Alpine Linux)

### 安装位置

- **安装目录**: `/var/apps/fnos-plugin-bun/`
- **可执行文件**: `/var/apps/fnos-plugin-bun/target/bin/bun`

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

1. Fork 本项目
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

## 📝 开发者

- **Bun 项目维护**: [Bun 官方 (oven-sh)](https://bun.com)
- **插件分发者**: [LF112 (futiwolf)](https://lf112.net)

## 📄 许可证

本项目遵循相应的开源许可协议。Bun 本身遵循 MIT 许可证。

## 🔗 相关链接

- [Bun 官方网站](https://bun.sh)
- [Bun 官方文档](https://bun.sh/docs)
- [Bun GitHub 仓库](https://github.com/oven-sh/bun)
- [飞牛OS 官网](https://www.fnnas.com)

## ⚠️ 免责声明

本插件仅为飞牛OS提供 Bun 运行时环境支持，Bun 软件本身由 oven-sh 开发和维护。使用本插件即表示您同意 Bun 的相关许可协议。

---

<div align="center">

**Enjoy coding with Bun on FnOS! 🎉**

Made with ❤️ by [LF112](https://lf112.net)

</div>
