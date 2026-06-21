# Walking Skeleton — GSD Hello World 網頁計算機

**Phase:** 1
**Generated:** 2026-06-21

## Capability Proven End-to-End

使用者直接在瀏覽器開啟 index.html，於兩個輸入框各填入一個數字，點擊任一運算按鈕（加/減/乘/除），即可在結果區塊看到正確的計算答案；無效輸入或除以零時顯示中文提示，頁面不壞掉。

## Architectural Decisions

| Decision | Choice | Rationale |
|---|---|---|
| Framework | 無框架 — 原生 HTML + JavaScript | 學習 GSD 工作流程為主目的，零依賴、零建置步驟、任何瀏覽器直接開啟，複雜度最低 |
| Data layer | 無 — 純記憶體即時計算 | 兩個數字相運算，結果直接顯示，不需任何持久化 |
| Auth | 無 | 個人學習工具，無使用者帳號概念 |
| Deployment target | 本機瀏覽器直接以 file:// 開啟 | 學習用途，「能在本機跑通」即視為完成 |
| Directory layout | 單一 index.html 置於 repo 根目錄 | 最小化結構，無子目錄，無建置產物 |

## Stack Touched in Phase 1

- [x] Project scaffold — index.html 本身即為完整應用，無額外框架初始化或建置步驟
- [x] Routing — 單頁應用，無路由需求
- [x] Database — 不適用（純記憶體計算，無讀寫需求）
- [x] UI — 兩個 `<input type="number">`、四顆 `<button>`（加/減/乘/除）、一個 `<div id="result">`，全部透過 JavaScript onclick 事件繫結至 calculate(op) 函式
- [x] Deployment — 在本機任何瀏覽器以 file:// 開啟 index.html 即完成完整執行路徑（此專案無伺服器層）

## Out of Scope（刻意排除，防止未來各階段重新爭議）

- 前端框架（React / Vue / Svelte 等）— 刻意排除，學習 GSD 流程優先，不引入框架複雜度
- 後端 / API / 資料庫 — 純前端單檔即可完成核心價值，不需伺服器
- 登入 / 使用者帳號 — 與核心計算功能無關
- UI 美化 / 響應式設計 / CSS 框架 — 學習用途，外觀不是重點
- 進階運算（括號、百分比、科學函式、連續運算、記憶功能）— 範圍越小越好，只做基本四則
- 部署至遠端（GitHub Pages / Vercel 等）— 本機能跑即視為完成
- 單元測試 / E2E 測試框架 — 驗證透過瀏覽器手動執行，無測試 runner

## Subsequent Slice Plan

此專案僅有 Phase 1，一個階段即為完整交付物。Walking Skeleton 完成後即視為專案收尾，無後續切片計畫。
