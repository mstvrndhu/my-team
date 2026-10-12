# Task: BMI Calculator App (zh-TW) / 任務：BMI 計算器（繁體中文台灣用語）

Date: 2026-10-12
From: Leader · Wailan (洄瀾)
To: Member · Taroko (太魯閣)

## What to do / 要做什麼

Build a simple **BMI calculator web app**. The whole user interface must be in **Traditional Chinese (Taiwan usage)** — e.g. 軟體, 資訊, 體重, 身高. No Simplified Chinese, no English labels in the UI.

## Format / 格式

- **One single self-contained HTML file** (`bmi-calculator.html`) — all CSS and JS inline, no external libraries, no internet needed to open it.
- Interface items (suggested wording, you may polish):
  - Title: 「BMI 計算器」
  - Input 1: 身高（公分 / cm）
  - Input 2: 體重（公斤 / kg）
  - Button: 計算
  - Result area: 顯示 BMI 數值（保留一位小數）＋ 分類結果
- BMI categories (Taiwan common standard):
  - 過輕：BMI < 18.5
  - 正常：18.5 ≤ BMI < 24
  - 過重（微胖）：24 ≤ BMI < 27
  - 肥胖：BMI ≥ 27
- Show the category with a color hint (e.g. 正常 = green, others = orange/red) and a friendly one-line tip.

## What "done" looks like / 怎樣算做完

1. File saved as a **new file** in `workspace/outbox/` (e.g. `20261012-bmi-calculator.html`).
2. Opening the file in a browser works offline; entering a valid height (e.g. 170) and weight (e.g. 65) and clicking 計算 shows 「BMI 22.5 → 正常」.
3. Bad input (empty, negative, letters) shows a zh-TW error message like 「請輸入有效的數字」 and does not crash.
4. All visible text is Traditional Chinese (Taiwan).
5. Add one handoff line in the outbox note: what you did, anything to watch, ready to use or not.

## Do not / 不要做

- Do not write into `workspace/shared/`.
- Do not install anything or use external libraries.
