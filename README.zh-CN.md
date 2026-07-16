# Laser Studio

**版本：V1.0.2**

语言：

- [English](README.md)
- [繁體中文](README.zh-TW.md)
- [Deutsch](README.de.md)
- [日本語](README.ja.md)

Laser Studio 是一款免费的桌面激光雕刻与激光切割软件。

LightBurn 很强大，LaserGRBL 也是一个实用的轻量选择。我开始做 Laser Studio，是因为免费的激光软件选择仍然比较少，尤其是带有现代化编辑流程的软件更少。Laser Studio 的目标，是参考 xTool 软件和拓竹 Bambu Studio 中比较实用的工作流，把项目管理、可视化编辑、设备设置、工艺参数、预览和执行整合到一个免费软件里。

Laser Studio 当前主要面向通过串口 G-code 流式控制的 GRBL 类 XY 平台激光雕刻机。

![Laser Studio 首页](screenshots/zh/home.png)

## 下载

可执行文件会放在 [releases](releases/) 目录中，或作为 GitHub Releases 附件发布。

当前可下载文件：

- Windows x64：[`LaserStudio-1.0.2-windows-x64-33335bc.zip`](releases/LaserStudio-1.0.2-windows-x64-33335bc.zip)
- macOS Apple Silicon：[`LaserStudio-v1.0.2-macOS-arm64.dmg`](releases/LaserStudio-v1.0.2-macOS-arm64.dmg)
- macOS Apple Silicon ZIP：[`LaserStudio-v1.0.2-macOS-arm64.zip`](releases/LaserStudio-v1.0.2-macOS-arm64.zip)
- macOS Intel：[`LaserStudio-v1.0.2-macOS-x86_64.dmg`](releases/LaserStudio-v1.0.2-macOS-x86_64.dmg)
- macOS Intel ZIP：[`LaserStudio-v1.0.2-macOS-x86_64.zip`](releases/LaserStudio-v1.0.2-macOS-x86_64.zip)
- SHA-256 校验值：[`checksums.txt`](releases/checksums.txt)
- 版本说明：[`release-notes-v1.0.2.md`](releases/release-notes-v1.0.2.md)

## V1.0.2 更新内容

- 新增启动自动检查和手动检查 GitHub Release 更新；后台失败静默处理，手动失败时提供发布页备用链接。
- 完善更新提示和系统设置等界面的五语言支持。
- 全新安装会跟随受支持的系统语言，无法匹配翻译时回退到英文。
- 完成材料名称、分类、说明、注意事项和工艺摘要的多语言适配。
- 加固 macOS 运行库部署、发布签名和真实启动验证。
- 扩展更新、语言配置、材料管理和图片 overscan 自动回归测试。

## 主要功能

### 项目工作流

- 创建、打开、保存和重新打开本地 Laser Studio 项目。
- 首页最近项目卡片可以快速继续之前的工作。
- 项目文件会保存可编辑对象、工作区信息、缩略图、工艺预设和素材引用。
- 当前项目格式围绕 `.lsproj` 设计，编辑项目数据和任务执行数据是分开的。

### 可视化编辑器

Laser Studio 提供面向激光加工准备的画布编辑器。

- 带毫米定位、标尺、缩放控制和适配视图的网格工作区。
- 支持对象位置、尺寸、旋转、镜像、对齐、顺序、布局、偏移、阵列和路径操作。
- 文字对象支持字体、字形、字号、行高、字间距、对齐和焊接设置。
- 支持导入图片，创建矢量对象、路径、矩形、画笔路径、二维码、标定对象、连接点和内置图形素材。
- 对象列表支持可见性、锁定状态、顺序、缩略图和对象级工艺参数。

![工作区编辑器](screenshots/zh/workspace.png)

### 内置图形库

左侧工具栏包含可复用的素材库，适合快速制作图案。当前版本包含基础几何图形、自然图形、动物、符号、贴纸和图标类素材。

![内置图形库](screenshots/zh/shape-library.png)

### 工艺参数

每个对象都可以设置独立的激光工艺预设。

支持的加工模式包括：

- 线雕
- 填充雕刻
- 线切割
- 图片雕刻

工艺参数包括：

- 激光光源选择
- 功率、最小功率、最大功率
- 加工速度，单位为 `mm/s`
- 加工次数
- 填充密度和线间距
- 填充顺序和填充路径
- 扫描角度
- 交叉填充
- Overscan
- 双向补偿
- 停顿时间
- 切缝补偿
- 切割断点
- 增强切割 / wobble cut 参数
- 栅格 DPI 和图片打点时间
- 图片阈值、Gamma、对比度、黑场、白场、抖动强度和反色
- 图片算法，包括灰度、蓝噪声、Bayer、Floyd-Steinberg、Jarvis、Stucki、Atkinson 和 Sierra 类抖动算法

### 打印机管理

Laser Studio 可以管理 GRBL 打印机配置和串口连接。

- 串口发现和连接。
- 保存打印机配置。
- 设置工作区宽度和高度。
- 设置原点位置。
- 配置激光光源和功率。
- 显示 GRBL 设置。
- 显示设备状态、`MPos` 和 `WPos`。
- 点动控制。
- 回原点、解锁、设置原点、暂停、继续、停止和关闭激光命令。
- 当设备支持回原点时，可选择任务开始前和完成后自动回到设备原点。

![打印机管理](screenshots/zh/printer-management.png)

### G-code 预览和打印控制

发送任务到设备之前，Laser Studio 会打开全尺寸打印任务工作区：左侧显示 G-code 命令流，中间显示路径预览，右侧提供打印控制。

- 带行号的 G-code 预览。
- 大任务会使用可见行窗口，避免界面卡顿。
- 中间路径预览可显示模拟运动以及已经发送的 G-code。
- 执行时高亮当前行。
- 开始、暂停、继续和停止控制。
- 设备状态和进度跟踪。
- 打印任务标签会持续显示进度，点击后可重新展开打印工作区。
- 对工作区范围和无效工艺参数进行安全检查。

![打印任务工作区](screenshots/zh/gcode-preview.png)

### G-code 模拟打印

模拟打印在同一个打印任务工作区中运行，可以在发送到设备前检查生成路径。进入模拟模式后，模拟控制会显示在路径预览下方。

- 在工作区中模拟刀路。
- 可调模拟速度。
- 可选显示空移路径。
- 显示解析行进度和运动状态。

![打印任务工作区中的 G-code 模拟打印](screenshots/zh/simulation.png)

## 当前范围

V1.0.2 聚焦可靠的桌面编辑、材料与工艺管理，以及面向 XY 激光雕刻机的 GRBL 串口流式执行。

当前重点：

- 本地项目编辑
- GRBL 设备连接
- G-code 生成
- G-code 预览
- G-code 模拟
- PC 端流式执行

计划中或持续完善的方向：

- 更广泛的设备支持
- 网络设备发现
- 控制器托管任务包
- 更多材料库和工艺预设
- 更多导入 / 导出兼容性

## 许可说明

Laser Studio 可以免费使用，但它是专有软件。源码不公开发布。

Laser Studio 使用 Qt。Qt 根据 LGPLv3 或对应 Qt 模块适用的开源许可提供。Laser Studio 动态链接 Qt 库，用户可以根据 Qt 适用许可条款替换或重新链接 Qt 动态库。

Qt 源码和许可信息：

- https://www.qt.io/
- https://www.qt.io/download-open-source
- https://www.gnu.org/licenses/lgpl-3.0.html
