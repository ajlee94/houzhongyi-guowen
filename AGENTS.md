# AGENTS.md

## 專案狀態

- 專案：後中醫國文
- 目前狀態：已完成初始資料夾與說明文件建立。
- 工作重點：整理國文備考資料、筆記、題目來源與輸出成果。

## 結構約定

- `input/` 放原始資料。
- `notes/` 放整理後筆記。
- `references/` 放參考來源與考情資料。
- `output/` 放輸出成果。
- `scripts/` 放可重複使用的處理腳本。

## 下一步

- 匯入第一批原始資料到 `input/`。
- 決定筆記命名規則，例如 `YYYY-來源-主題.md` 或 `單元-主題.md`。
- 若開始建立題庫或索引，先定義欄位格式再批次整理。

## Project Memory

### Current Mode

- 專案目前在建立「高中古文資料庫」與行動友善閱讀前端。
- 資料架構採用：Google Sheets 當資料庫，GitHub Pages 當前端。
- 正式 Google Sheet：
  - `https://docs.google.com/spreadsheets/d/11BZATYOd-QuuYzVDZMVY2k-eGd5Z69m7vlb6R80o4Nw/edit?usp=sharing`
  - 已確認公開 CSV 可讀，GitHub Pages 前端可用 `gviz/tq?tqx=out:csv` 讀取。

### Latest Outputs

- `index.html`：GitHub Pages 首頁，直接讀取 Google Sheets CSV，包含搜尋、官方40篇/其他分類篩選、手機友善閱讀介面。
- `output/highschool-classics-40.html`：本地版行動閱讀頁，含橫向篇目卡片、固定搜尋列、可展開內容區塊。
- `output/高中古文40篇正式資料庫.csv`：用國語文學科中心「古典名篇」前40篇建出的正式資料 CSV。
- `scripts/build_classics40_formal.py`：從國語文學科中心清單與頁面擷取前40篇原文並產生 CSV 的腳本。

### Commands

- 重新產生正式 CSV：
  - `C:\Users\a5207\.cache\codex-runtimes\codex-primary-runtime\dependencies\python\python.exe E:\我的雲端硬碟\codex\後中醫\國文\scripts\build_classics40_formal.py`
- 檢查 Git 狀態：
  - `git -C 'E:\我的雲端硬碟\codex\後中醫\國文' status --short`

### Rules

- 正式40篇清單以國語文學科中心「古典名篇」前40篇為基準，不再混入其他版本。
- 其他有用古文可留在同一份 Sheets，但必須以 `其他分類：...` 標示，不能混入官方前40篇。
- 原文欄只放可追溯來源；來源未補齊時標 `待補可靠原文來源`。
- 註釋、翻譯、賞析要根據原文整理，不直接複製商業教材。
- GitHub Pages 前端應從 Google Sheets 讀資料，不把整份資料硬寫死在 HTML。

### Next Steps

- GitHub 部署仍未完成：本地 `gh auth status` 顯示未登入；GitHub plugin 目前查不到 installations/accounts/repos。
- 若要部署 GitHub Pages，先完成其中一項：
  - 在 PowerShell 執行 `gh auth login`，或
  - 授權 GitHub connector 到可用帳號/repo。
- 部署後要確認 GitHub Pages URL 可讀取 Google Sheets CSV。
- 延伸篇第41-50列中，部分篇目仍需補可靠原文來源：
  - `訓儉示康`
  - `上樞密韓太尉書`
  - `指喻`
  - `東番記`
  - `紀水沙連`
  - `賣柑者言`
  - `病梅館記`

### Last Shutdown Sync

- Date: 2026-05-06 00:35 +08:00
- Summary: 建立正式 Google Sheets 資料庫，改用官方前40篇為基準；追加其他分類延伸篇；建立 `index.html` 作為 GitHub Pages 前端，從 Sheets CSV 動態讀取；更新本地行動版閱讀頁。
- Manual actions: 完成 GitHub 登入或 connector 授權後，才能建立/推送 repo 並開啟 GitHub Pages。
