# Requirements: GSD Hello World — 網頁計算機

**Defined:** 2026-06-21
**Core Value:** 在瀏覽器打開 index.html，輸入兩個數字、按下任一運算按鈕，就能看到正確的計算結果。

## v1 Requirements

Requirements for initial release. Each maps to roadmap phases.

### 介面 (UI)

- [x] **UI-01**: 頁面有兩個數字輸入框，使用者各輸入一個數字
- [x] **UI-02**: 頁面有「加」「減」「乘」「除」四顆按鈕
- [x] **UI-03**: 頁面有獨立的結果顯示區塊

### 運算 (CALC)

- [x] **CALC-01**: 按「加」顯示兩數之和
- [x] **CALC-02**: 按「減」顯示兩數之差
- [x] **CALC-03**: 按「乘」顯示兩數之積
- [x] **CALC-04**: 按「除」顯示兩數之商

### 錯誤處理 (ERR)

- [x] **ERR-01**: 除以零時顯示可理解的提示，頁面不壞掉
- [x] **ERR-02**: 輸入非數字或空白時顯示可理解的提示，頁面不壞掉

## v2 Requirements

(無 — 範圍刻意維持最小)

## Out of Scope

Explicitly excluded. Documented to prevent scope creep.

| Feature | Reason |
|---------|--------|
| 前端框架（React/Vue 等） | 刻意用原生 HTML + JS，零依賴、跑通流程優先 |
| 後端／API／資料庫 | 純前端單檔即可完成核心價值 |
| 登入／使用者帳號 | 與核心價值無關 |
| UI 美化／響應式設計 | 學習用，外觀不是重點 |
| 進階運算（括號、百分比、科學函式、連續運算） | 範圍越小越好，只做基本四則 |
| 部署（GitHub Pages 等） | 本地能跑即視為完成 |

## Traceability

Which phases cover which requirements. Updated during roadmap creation.

| Requirement | Phase | Status |
|-------------|-------|--------|
| UI-01 | Phase 1 | Complete |
| UI-02 | Phase 1 | Complete |
| UI-03 | Phase 1 | Complete |
| CALC-01 | Phase 1 | Complete |
| CALC-02 | Phase 1 | Complete |
| CALC-03 | Phase 1 | Complete |
| CALC-04 | Phase 1 | Complete |
| ERR-01 | Phase 1 | Complete |
| ERR-02 | Phase 1 | Complete |

**Coverage:**

- v1 requirements: 9 total
- Mapped to phases: 9 ✓
- Unmapped: 0 ✓

---
*Requirements defined: 2026-06-21*
*Last updated: 2026-06-21 after roadmap creation*
