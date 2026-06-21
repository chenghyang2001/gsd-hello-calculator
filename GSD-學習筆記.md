# GSD 學習筆記 — 操作小抄 + 概念總複習

> 從一個「網頁計算機 Hello World」實作中學會的 GSD（Get Shit Done）。
> GSD 是對抗「上下文腐化」的 Claude Code 工作流框架，作者 TÂCHES，套件名 `get-shit-done-cc`。
> 本機安裝版本：v1.42.3（全域裝在 `~/.claude`）。

---

## 一句話總結

> **GSD = 用「四階段循環」逼出品質 + 用「隔離乾淨 context」對抗 AI 變笨 + 用「markdown 檔當外接記憶」讓 AI 永遠記得專案。**

---

## 一、四階段循環（GSD 骨架）

| 階段 | 在做什麼 | 對應指令 | 產出 |
|---|---|---|---|
| 1. 討論 Discuss | 反問你「要建什麼」，釐清需求 | `/gsd-new-project` 的問答 | `PROJECT.md`、`REQUIREMENTS.md`、`ROADMAP.md` |
| 2. 規劃 Plan | 把一個 phase 拆成具體任務 | `/gsd-plan-phase N` | `NN-NN-PLAN.md`、`SKELETON.md` |
| 3. 執行 Execute | 子代理照計畫實作 + 自我驗收 | `/gsd-execute-phase N` | 程式碼、`SUMMARY.md` |
| 4. 驗證 Verify | 機器驗邏輯 + 人肉眼驗體感 + 打 `approved` | human-UAT gate | `VERIFICATION.md`、`HUMAN-UAT.md` |

**重點**：先講清楚要什麼 → 再規劃怎麼做 → 才動手做 → 最後驗收。新手最容易跳過 1、2 直接做；GSD 強迫照順序，品質才穩。

---

## 二、兩大靈魂

### 隔離（Isolation）= 對抗上下文腐化

- 每個階段之間打 `/clear` 清空對話。
- `execute-phase` 會「派子代理」去做，子代理本來就在全新乾淨 context 開工。
- 為什麼：對話塞滿失敗紀錄/舊訊息會讓 AI「越用越笨」。隔離讓每次幹活都是最清醒狀態。

### Markdown 外接記憶

- `/clear` 清掉的是「短期對話」，保留的是 `.planning/` 裡的 markdown 檔。
- 所以清空後 GSD 還記得整個專案——它讀 `STATE.md` / `PLAN.md` 等檔接續。
- 「清空 vs 記得」這對矛盾就是這樣解決的。

---

## 三、GSD 的品質防護（比直接叫 AI 寫高明的地方）

1. **需求自動補錯誤處理**：只說「加減乘除」，GSD 主動補「除以零」「非數字」的處理——擋住「只寫快樂路徑」。
2. **UI 安全閘（UI Gate）**：偵測有 UI 卻沒設計合約會停下來問；範圍寫清楚（如「美化 out of scope」），它能自動建議跳過。
3. **STRIDE 威脅模型**：連小計算機都強制 `textContent`、禁 `innerHTML`/`eval()`（防 XSS）。
4. **雙層驗收**：機器先 grep + 模擬執行，最後留「人工目視閘」給人——機器證邏輯、人證體感。

---

## 四、指令小抄

### 核心流程

```
/gsd-new-project        # 開新專案：討論→需求→路線圖
/clear
/gsd-plan-phase <N>     # 規劃第 N 階段
/clear
/gsd-execute-phase <N>  # 執行第 N 階段
# → 最後打 approved 通過驗收
```

### 輔助

```
/gsd-progress           # 看進度 + 建議下一步
/gsd-help               # 查所有指令
/gsd-resume-work        # 隔天回來接續（讀 STATE.md）
/gsd-phase "描述"       # 在既有專案加一個新 phase
/gsd-autonomous         # 自動跑完剩下所有 phase（熟了再用）
/gsd-debug "問題"       # 系統化除錯
```

### 🔑 鐵則

- GSD 文件都寫冒號 `/gsd:xxx`，**本機要打連字號 `/gsd-xxx`**（冒號→連字號，參數照舊）。
- 兩個 slash 指令不能打在同一行：`/clear` 是 CLI 內建、按 Enter 立刻清空，要分兩次 Enter。
- `/clear` 是「建議」不是「必須」——executor 是獨立乾淨子代理，context 不大時可直接 execute。

---

## 五、專案產物地圖

```
gsd-hello-calculator/
├── index.html              ← 成品
├── README.md
├── GSD-學習筆記.md          ← 本檔
└── .planning/              ← GSD 的大腦
    ├── PROJECT.md          願景
    ├── REQUIREMENTS.md     9 條需求（UI-01~03 / CALC-01~04 / ERR-01~02）
    ├── ROADMAP.md          1 個 phase
    ├── STATE.md            專案記憶
    └── phases/01-working-calculator/
        ├── 01-01-PLAN.md
        ├── SKELETON.md
        ├── 01-01-SUMMARY.md
        ├── 01-VERIFICATION.md
        └── 01-HUMAN-UAT.md
```

`.planning/` 整包 = 「任何人或未來的你/AI 接手都能秒懂專案」的交接文件。

---

## 六、本次實作的設定選擇（為什麼這樣選）

| 設定 | 選擇 | 原因 |
|---|---|---|
| Mode | Interactive | 學流程要看到每步確認（YOLO 會自動衝完看不清） |
| Granularity | Coarse | 小專案階段越少越好 |
| Execution | Sequential | 只有一個任務 |
| Git Tracking | Yes | 看得到 `.planning/` 進 git |
| Research | No | 計算機不需研究，省 token |
| Plan Check | No | 太小不需要 |
| Verifier | Yes | 才會走到第 4 階段驗證 |
| 結構模式 | Vertical MVP | 一次交付端到端可用功能 |
| UI Gate | 跳過 UI-SPEC | 美化已明訂 out of scope |

---

## 七、延伸練習

1. 加 phase 練擴充：`/gsd-phase "加上清除按鈕和鍵盤輸入"` → `/gsd-plan-phase 2` → `/gsd-execute-phase 2`
2. 體驗自動：`/gsd-autonomous`
3. 體驗除錯：故意改壞 `index.html`，`/gsd-debug "除法壞了"`

---

## 附：GSD 跨工具

GSD 官方支援多種 AI CLI（Claude Code / Codex / Gemini / OpenCode / Cursor … by TÂCHES）。
本機只裝了 Claude 版（`--claude --global`）。要給 Codex 用需另跑 `npx get-shit-done-cc --codex --global`。
