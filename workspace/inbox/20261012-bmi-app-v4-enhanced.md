# Task: BMI 計算器 v4 — 強化版（更多細節＋更多操作）/ 任務單

Date: 2026-10-12
From: Leader · Wailan (洄瀾)
To: Member · Taroko (太魯閣)

## Context / 背景

小隊長已確認 v3 的 revert 是他的決定，**v4 直接從 v2 繼續**。基底檔：`workspace/outbox/20261012-bmi-calculator.html`（v2）。不要復活 v3。

## What to do / 要做什麼

Build an improved **v4** BMI calculator: richer result details + more actions for the user. UI stays **繁體中文（台灣用語）**, single self-contained HTML file, fully offline, no external libraries.

## A. More detailed results / 更多計算細節

Keep v2's category logic, colors, tips. Result card additionally shows:

1. **健康體重範圍** — for the entered height, the weight range for BMI 18.5–24 (e.g. 170 cm → 53.5–69.4 公斤), one decimal.
2. **理想體重** — BMI 22 × height(m)², one decimal (170 cm → 63.6 公斤).
3. **距離正常體重** — in kg: 「需減重 X 公斤」/「需增重 X 公斤」/「體重已在正常範圍內」.
4. **Optional inputs 年齡與性別** (age number field + 男/女 radio): when both provided, also show
   - **基礎代謝率（BMR）** via Mifflin-St Jeor: 男 = 10×kg + 6.25×cm − 5×age + 5；女 = 10×kg + 6.25×cm − 5×age − 161（整數 kcal/日）
   - **一日建議熱量（靜態生活推估）** = BMR × 1.2，註明「依久坐生活型態估算」
   - If age/sex not filled in: hide this block silently — optional fields, **not** an error.
   - If age given but out of 1–120 → localized error「請輸入有效的年齡（1–120）」and hide BMR block.

## B. More user actions / 更多使用者操作

1. **歷史紀錄（localStorage）**: every successful calculation saved (time, 身高, 體重, BMI, 體位). Shown as a list below the result; **click a record → reloads those values into the inputs and recalculates**. Each record has 刪除 (single) and there's 清除全部. Keep newest 20 max. If localStorage is unavailable, hide the feature with a zh-TW note — no crash.
2. **複製結果 button**: copies a formatted summary to clipboard (e.g. 「BMI 計算結果：170 cm／65 kg → BMI 22.5（正常）」) via `navigator.clipboard` with a fallback; brief 「已複製」 feedback.
3. **列印 button**: `window.print()` with a `@media print` stylesheet so the printout shows only the result card + reference table (no buttons/inputs/history).
4. Keep **重設** and Enter-to-calculate exactly as v2.

## C. Keep from v2 / 要保留的

- zh-TW-only interface, single file, offline, no libraries
- Validation: height 50–250, weight 10–300, same 4 error types in zh-TW
- a11y: `role="alert"`, `aria-live`, `aria-invalid`, focus to first bad input
- Layout, colors, 衛福部 reference table

## What "done" looks like / 怎樣算做完

1. New file `workspace/outbox/20261012-bmi-calculator-v4.html` — **v1/v2 untouched**, v3 stays gone.
2. Test case 170 cm / 65 kg / 30 歲 / 男 → BMI 22.5 正常；健康範圍 53.5–69.4 公斤；理想體重 63.6 公斤；「體重已在正常範圍內」；BMR ≈ 1568 kcal/日；一日建議熱量 ≈ 1881 kcal.
3. Test case 170 cm / 72.3 kg → BMI 25.0 過重（微胖）；顯示「需減重 2.9 公斤」.
4. Two calculations → 2 history records; click old record → inputs reload + recalc; 刪除/清除全部 work; page refresh → records persist.
5. 複製結果 → clipboard contains the formatted summary; 列印 → clean printout of result + table only.
6. Bad input still blocked in zh-TW, no crash, works fully offline.
7. One handoff line in outbox: what you did, what to watch, ready to use or not.

## Git / 版本控制

Local commit of your finished file is fine. **Do NOT push to GitHub** without the captain's approval.

## Do not / 不要做

- Do not modify v1/v2 files; do not restore v3; no external libraries, fonts, or network calls; no writes into `workspace/shared/`.
