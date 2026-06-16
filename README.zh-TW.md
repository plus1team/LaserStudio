# Laser Studio

**版本：V0.9.3**

語言：

- [English](README.md)
- [简体中文](README.zh-CN.md)
- [Deutsch](README.de.md)
- [日本語](README.ja.md)

Laser Studio 是一款免費桌面軟體，適用於雷射／激光雕刻與切割工作流程。

LightBurn 功能完整，LaserGRBL 也是實用的輕量選擇。我開始開發 Laser Studio，是因為免費雷射加工軟體仍然不多，特別是具備現代化編輯流程的選擇更少。Laser Studio 的目標，是參考 xTool 軟體和 Bambu Studio（拓竹）中實用的工作流程，把專案管理、視覺化編輯、裝置設定、工藝參數、預覽和執行整合到同一套免費軟體裡。

Laser Studio 目前主要面向透過序列埠（串口）G-code 串流控制的 GRBL 類 XY 平台雷射雕刻機。

![Laser Studio 首頁](screenshots/zh/home.png)

## 下載

執行檔會放在 [releases](releases/) 目錄中，或作為 GitHub Releases 附件發布。

目前可下載檔案：

- Windows x64：[`LaserStudio-0.9.3-windows-x64-39e4ebf.zip`](releases/LaserStudio-0.9.3-windows-x64-39e4ebf.zip)
- macOS Apple Silicon：[`LaserStudio-v0.9.3-macOS-arm64.dmg`](releases/LaserStudio-v0.9.3-macOS-arm64.dmg)
- macOS Apple Silicon ZIP：[`LaserStudio-v0.9.3-macOS-arm64.zip`](releases/LaserStudio-v0.9.3-macOS-arm64.zip)
- macOS Intel：[`LaserStudio-v0.9.3-macOS-x86_64.dmg`](releases/LaserStudio-v0.9.3-macOS-x86_64.dmg)
- macOS Intel ZIP：[`LaserStudio-v0.9.3-macOS-x86_64.zip`](releases/LaserStudio-v0.9.3-macOS-x86_64.zip)
- SHA-256 校驗值：[`checksums.txt`](releases/checksums.txt)
- 版本說明：[`release-notes-v0.9.3.md`](releases/release-notes-v0.9.3.md)

## 主要功能

### 專案工作流程

- 建立、開啟、儲存和重新開啟本機 Laser Studio 專案。
- 首頁最近專案卡片可快速接續之前的工作。
- 專案檔會儲存可編輯物件、工作區資訊、縮圖、工藝預設和素材參照。
- 目前專案格式以 `.lsproj` 為核心設計，編輯用的專案資料會和任務執行資料分開。

### 視覺化編輯器

Laser Studio 內建用於準備雷射加工任務的畫布編輯器。

- 具備毫米定位、尺規、縮放控制和自動適配視圖的格線工作區。
- 支援物件位置、尺寸、旋轉、鏡射、對齊、順序、佈局、偏移、陣列和路徑操作。
- 文字物件支援字型、字重樣式、字號、行高、字距、對齊和焊接設定。
- 支援匯入圖片，建立向量物件、路徑、矩形、筆刷路徑、QR Code、校正物件、連接點和內建圖形素材。
- 物件列表支援可見性、鎖定狀態、順序、縮圖和物件級工藝設定。

![工作區編輯器](screenshots/zh/workspace.png)

### 內建圖形庫

左側工具列包含可重複使用的素材庫，方便快速製作圖案。現有版本包含基礎幾何圖形、自然圖形、動物、符號、貼紙和圖示類素材。

![內建圖形庫](screenshots/zh/shape-library.png)

### 工藝設定

每個物件都可以指定自己的雷射工藝預設。

支援的加工模式包括：

- 線條雕刻
- 填充雕刻
- 線條切割
- 圖片雕刻

工藝參數包括：

- 雷射光源選擇
- 功率、最小功率、最大功率
- 加工速度，單位為 `mm/s`
- 加工次數
- 填充密度和線距
- 填充順序和填充路徑
- 掃描角度
- 交叉填充
- Overscan
- 雙向補償
- 停頓時間
- 切縫補償
- 切割斷點
- 強化切割 / wobble cut 參數
- Raster DPI 和圖片打點時間
- 圖片閾值、Gamma、對比度、黑場、白場、抖動強度和反色
- 圖片演算法，包括灰階、藍噪聲、Bayer、Floyd-Steinberg、Jarvis、Stucki、Atkinson 和 Sierra 類抖動演算法

### 印表機管理

Laser Studio 可以管理 GRBL 印表機設定檔和序列埠連線。

- 偵測和連線序列埠。
- 儲存印表機設定檔。
- 設定工作區寬度和高度。
- 設定原點位置。
- 設定雷射光源和功率。
- 顯示 GRBL 設定。
- 顯示裝置狀態、`MPos` 和 `WPos`。
- Jog 點動控制。
- 回原點、解鎖、設定原點、暫停、繼續、停止和關閉雷射命令。
- 當裝置支援回原點時，可選擇任務開始前和完成後自動回到裝置原點。

![印表機管理](screenshots/zh/printer-management.png)

### G-code 預覽和列印控制

把任務送到裝置之前，Laser Studio 會先將專案編譯成可執行的 G-code，並顯示產生的命令串流。

- 帶行號的 G-code 預覽。
- 大型任務會使用可見行視窗，避免介面卡頓。
- 執行時高亮目前行。
- 開始、暫停、繼續和停止控制。
- 裝置狀態和進度追蹤。
- 對工作區範圍和無效工藝設定進行安全檢查。

![G-code 預覽](screenshots/zh/gcode-preview.png)

### G-code 模擬列印

Laser Studio 內建 G-code 模擬視窗，可在送出到裝置前檢查產生的路徑。

- 在工作區中模擬刀路。
- 可調整模擬速度。
- 可選擇顯示空移路徑。
- 顯示解析行進度和運動狀態。

![G-code 模擬列印](screenshots/zh/simulation.png)

## 目前範圍

V0.9.3 聚焦桌面編輯，以及面向 XY 雷射雕刻機的 GRBL 序列埠串流執行。

目前重點：

- 本機專案編輯
- GRBL 裝置連線
- G-code 產生
- G-code 預覽
- G-code 模擬
- PC 端串流執行

規劃中或持續完善的方向：

- 更廣泛的裝置支援
- 網路裝置探索
- 由控制器託管的任務包
- 更多材料庫和工藝預設
- 更多匯入 / 匯出相容性

## 授權說明

Laser Studio 可以免費使用，但它是專有軟體。原始碼不公開發布。

Laser Studio 使用 Qt。Qt 根據 LGPLv3 或對應 Qt 模組適用的開源授權提供。Laser Studio 動態連結 Qt 函式庫，使用者可以根據 Qt 適用授權條款替換或重新連結 Qt 動態函式庫。

Qt 原始碼和授權資訊：

- https://www.qt.io/
- https://www.qt.io/download-open-source
- https://www.gnu.org/licenses/lgpl-3.0.html
