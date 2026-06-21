# Roadmap: GSD Hello World — 網頁計算機

## Overview

單一 `index.html` 檔案，實作兩個數字輸入框、四顆運算按鈕、一個結果顯示區塊，並在除以零或非數字輸入時給出可理解的提示。全部需求在一個階段內完成，開啟瀏覽器即可驗收。

## Phases

**Phase Numbering:**

- Integer phases (1, 2, 3): Planned milestone work
- Decimal phases (2.1, 2.2): Urgent insertions (marked with INSERTED)

Decimal phases appear between their surrounding integers in numeric order.

- [x] **Phase 1: Working Calculator** - 在瀏覽器開啟 index.html，輸入兩個數字、按下四則運算按鈕，看到正確結果；無效輸入有可理解的提示 (completed 2026-06-21)

## Phase Details

### Phase 1: Working Calculator

**Goal**: 使用者可在瀏覽器直接開啟 index.html，輸入兩個數字並按下任一運算按鈕，看到正確的計算結果；除以零或非數字輸入時出現可理解的提示，頁面不壞掉
**Mode:** mvp
**Depends on**: Nothing (first phase)
**Requirements**: UI-01, UI-02, UI-03, CALC-01, CALC-02, CALC-03, CALC-04, ERR-01, ERR-02
**Success Criteria** (what must be TRUE):

  1. 使用者開啟 index.html 後，頁面上可見兩個數字輸入框、「加」「減」「乘」「除」四顆按鈕、以及一個結果顯示區塊
  2. 使用者在兩個輸入框各填入數字後，點擊任一運算按鈕，結果區塊顯示正確的計算答案
  3. 使用者在第二個輸入框填入 0 並按「除」，結果區塊顯示可理解的除以零提示訊息，頁面繼續正常運作
  4. 使用者在任一輸入框留白或輸入非數字並按下任一按鈕，結果區塊顯示可理解的錯誤提示訊息，頁面繼續正常運作
**Plans**: 1 plan
**UI hint**: yes

Plans:

- [x] 01-01-PLAN.md — 建立完整計算機 index.html（Walking Skeleton：UI + 四則運算 + 錯誤處理）

## Progress

**Execution Order:**
Phases execute in numeric order: 1

| Phase | Plans Complete | Status | Completed |
|-------|----------------|--------|-----------|
| 1. Working Calculator | 1/1 | Complete   | 2026-06-21 |
