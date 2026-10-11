<div align="center">

# EMBARCADERO DEV-C++ // CCODE

**面向 Windows 的 Delphi/C++ 开发环境源码。**<br>
*Source for a lightweight Windows C/C++ IDE built with Delphi.*

[![GitHub](https://img.shields.io/badge/GitHub-kerntau%2Fccode-181717?style=for-the-badge&logo=github)](https://github.com/kerntau/ccode)
[![C%2B%2B](https://img.shields.io/badge/C%2B%2B-IDE-00599C?style=for-the-badge&logo=cplusplus&logoColor=ffffff)](https://isocpp.org)
[![Delphi](https://img.shields.io/badge/Delphi-10.4%2B-E62431?style=for-the-badge)](https://www.embarcadero.com/products/delphi)
[![MinGW](https://img.shields.io/badge/MinGW-GCC-4EAA25?style=for-the-badge)](https://www.mingw-w64.org)

</div>

---

## 01. PROJECT PURPOSE // 项目定位

本仓库保存 Embarcadero Dev-C++ 的 IDE 源码、VCL 组件、资源、语言包和辅助工具。它继承 Bloodshed Dev-C++ 与 Orwell Dev-C++ 的开源工作，主程序使用 Delphi 构建，并通过 MinGW/GCC 提供 C/C++ 工具链。

## 02. TECHNICAL ARCHITECTURE // 技术架构

~~~mermaid
graph LR
    A[Delphi VCL source] --> B[CompileResources.bat]
    B --> C[DevCpp packages and resources]
    C --> D[devcpp.exe]
    E[MinGW GCC] --> D
    F[Source Tools] --> G[ConsolePauser and portable tools]
~~~

## 03. TECHNICAL MATRIX // 技术矩阵

| 模块 | 实现 | 说明 |
| --- | --- | --- |
| IDE | Delphi VCL | 编辑器、项目、调试和环境设置 |
| 编译器 | MinGW/GCC | C/C++ 编译与链接 |
| 编辑器 | SynEdit 及相关 VCL 组件 | 语法高亮和代码编辑 |
| 格式化 | AStyle、ClangFormat | C/C++ 代码格式化 |
| 资源 | RC、DFM、图标和字体 | Windows 界面与语言资源 |
| 辅助工具 | ConsolePauser、portable launcher | 运行控制台程序和便携配置 |

## 04. REPOSITORY TOPOLOGY // 源码工程拓扑

~~~text
.
├── Source/                   # Delphi 主程序、VCL 组件和测试
│   ├── VCL/                  # DevCpp、SynEdit 等包
│   ├── Tools/                # 辅助工具源码
│   ├── CompileResources.bat  # 编译资源
│   └── README.txt            # 完整构建说明
├── Lang/                     # 翻译文件
├── Icons/、Fonts/             # 资源
├── AStyle/、ClangFormat/      # 格式化组件
├── Help/                     # 帮助
├── NEWS.txt                  # 版本记录
└── SECURITY.md               # 安全报告入口
~~~

## 05. CLONE & QUICK START // 极速装配指南

完整编译需要 Windows、Delphi 10.4+ 和 MinGW/GCC。

~~~bash
git clone https://github.com/kerntau/ccode.git
cd ccode
~~~

随后按 Source/README.txt 操作：安装 VCL Style，编译 DevCpp.dpk、SynEdit、ClassBrowsing 和 SVGIconImageList 包，运行 Source/CompileResources.bat，再打开主程序工程。Windows Delphi 工程不能用 npm 或 Linux 工具链替代。

## 06. DEPLOYMENT & VERIFICATION // 部署与验证

构建主程序和辅助工具后，在干净 Windows 环境启动 devcpp.exe，验证编辑、编译、调试、资源加载和语言切换。提交前运行 Source/CleanSource.bat 清理旧生成物，并检查 NEWS.txt 与 SECURITY.md。

## 07. LICENSE // 许可证

许可证文本见 LICENSE 和 COPYING.txt；第三方组件遵循各自许可证。
