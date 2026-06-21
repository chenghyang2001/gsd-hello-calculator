# GSD Hello World — 網頁計算機

## What This Is

一個最簡單的網頁計算機，純學習用途。單一 `index.html`，用原生 HTML + JavaScript 實作：兩個數字輸入框、加減乘除四顆按鈕、一個顯示結果的區塊。給專案作者自己拿來熟悉 GSD 工作流程，不是給終端使用者的產品。

## Core Value

在瀏覽器打開 `index.html`，輸入兩個數字、按下任一運算按鈕，就能看到正確的計算結果。這條路徑跑通，專案就成立。

## Requirements

### Validated

<!-- Shipped and confirmed valuable. -->

(None yet — ship to validate)

### Active

<!-- Current scope. Building toward these. -->

- [ ] 使用者可以在兩個輸入框各輸入一個數字
- [ ] 使用者可以按「加」「減」「乘」「除」四顆按鈕各觸發對應運算
- [ ] 計算結果顯示在獨立的結果區塊
- [ ] 除以零時給出可理解的提示，不讓頁面壞掉
- [ ] 非數字／空白輸入時給出可理解的提示，不讓頁面壞掉

### Out of Scope

<!-- Explicit boundaries. Includes reasoning to prevent re-adding. -->

- 任何前端框架（React/Vue 等） — 刻意用原生 HTML + JS，保持零依賴、跑通流程優先
- 後端／API／資料庫 — 純前端單檔即可完成核心價值
- 登入／使用者帳號 — 與核心價值無關
- UI 美化／響應式設計 — 學習用，外觀不是重點
- 進階運算（括號、百分比、科學函式、連續運算） — 範圍越小越好，只做基本四則
- 部署（GitHub Pages 等） — 本地能跑即視為完成

## Context

- 技術環境：Windows 10，原生 HTML + JavaScript，瀏覽器直接開啟單檔執行。
- 專案性質：GSD 工作流 hello-world 練習，重點是走完「需求 → roadmap → 規劃 → 執行」的完整流程，而非功能堆疊。
- 已有檔案：`README.md`（僅標題）。

## Constraints

- **Tech stack**: 單一 `index.html`，原生 HTML + JavaScript，零框架、零建置工具 — 保持最小依賴，學習成本最低
- **Scope**: 範圍越小越好，只做基本四則 — 目的是跑通流程而非功能完整
- **Architecture**: 純前端、無後端 — 核心價值不需要伺服器

## Key Decisions

<!-- Decisions that constrain future work. Add throughout project lifecycle. -->

| Decision | Rationale | Outcome |
|----------|-----------|---------|
| 用原生 HTML + JS，不用框架 | 零依賴、學習流程優先 | — Pending |
| 全部塞進單一 index.html | 範圍越小越好，免建置 | — Pending |
| 只做基本四則運算 | 跑通 GSD 流程比功能多重要 | — Pending |
| 本地能跑即完成，不部署 | 縮小範圍 | — Pending |

## Evolution

This document evolves at phase transitions and milestone boundaries.

**After each phase transition** (via `/gsd-transition`):

1. Requirements invalidated? → Move to Out of Scope with reason
2. Requirements validated? → Move to Validated with phase reference
3. New requirements emerged? → Add to Active
4. Decisions to log? → Add to Key Decisions
5. "What This Is" still accurate? → Update if drifted

**After each milestone** (via `/gsd:complete-milestone`):

1. Full review of all sections
2. Core Value check — still the right priority?
3. Audit Out of Scope — reasons still valid?
4. Update Context with current state

---
*Last updated: 2026-06-21 after initialization*
