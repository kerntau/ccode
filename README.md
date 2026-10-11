# Embarcadero Dev-C++（ccode）

这是 Embarcadero Dev-C++ 的源代码仓库：一个面向 Windows 的轻量级 C/C++ 集成开发环境（IDE）。项目基于 Bloodshed Dev-C++ 与 Orwell Dev-C++ 的开源工作成果，使用 MinGW 版 GCC，也可以配置 Cygwin 等工具链。

## 项目能力

- C/C++ 语法高亮、代码补全和类浏览器
- 函数列表、代码洞察与可配置的格式化工具
- GDB 调试、GPROF 性能分析和资源文件编辑
- 创建控制台程序、静态库和 DLL，支持项目模板
- Makefile 生成、工具管理、打印、查找替换和多语言界面
- 可选的 DevPak 包管理器与扩展支持

该仓库主要保存 IDE 源码、资源、语言包和第三方组件；构建产物和完整安装包不随源码提交。

## 目录结构

| 路径 | 内容 |
| --- | --- |
| `Source/` | Delphi 主程序源码、窗体、编辑器、调试器、项目系统和测试 |
| `Source/VCL/` | VCL 组件、SynEdit、SVGIconImageList 等依赖 |
| `Source/Tools/` | ConsolePauser、便携版启动器等辅助工具 |
| `Lang/` | 翻译文件 |
| `Icons/`、`Fonts/` | 图标和字体资源 |
| `AStyle/`、`ClangFormat/` | 代码格式化相关资源 |
| `Help/` | 帮助文件 |
| `NEWS.txt` | 历史版本变更记录 |
| `Source/README.txt` | 更完整的 Delphi 编译和辅助工具说明 |

## 从源码构建（Windows）

完整构建需要 Windows 和 Delphi 10.4 或更高版本，并准备 MinGW/GCC 运行环境。

1. 在 Delphi IDE 中安装 `VCL Style - Windows10BlueWhale`。
2. 按 `Source/README.txt` 中的顺序编译并安装这些包：

   - `Source/VCL/DevCpp.dpk`
   - `Source/VCL/SynEdit/Packages/Sydney/Delphi/SynEditDelphi.groupproj`
   - `Source/VCL/ClassBrowsing/ClassBrowsing.dpk`
   - `Source/VCL/SVGIconImageList/Packages/D10_4/SVGIconImageListGroupPackages.groupproj`

3. 运行 `Source/CompileResources.bat` 编译资源。
4. 在 Delphi 中打开主程序工程并编译 `devcpp.exe`。如果出现模块或资源找不到，请先确认上述包已安装且工程搜索路径正确。
5. 提交改动或排查旧编译文件前，可运行 `Source/CleanSource.bat` 清理生成文件。

ConsolePauser、`devcppPortable.exe` 和旧版 `Packman.exe` 的构建方式也记录在 `Source/README.txt` 的“Compiling associated tools”部分。首次构建建议先只验证主程序，再按需构建这些工具。

## 开发提示

- 修改语言、图标或组件资源后，请重新运行资源编译脚本。
- 不要把本地 Delphi 配置、编译输出或个人路径提交到仓库；提交前检查 `.gitignore`。
- 版本变化和已知问题请参考 `NEWS.txt`，安全问题请按 `SECURITY.md` 的说明报告。

## 许可证与致谢

许可证文本见 [`LICENSE`](./LICENSE) 和 [`COPYING.txt`](./COPYING.txt)。项目沿用了 Dev-C++、SynEdit、FastMM、AStyle、Abbrevia 等开源组件；各组件的许可证和来源说明保留在仓库及对应目录中。
