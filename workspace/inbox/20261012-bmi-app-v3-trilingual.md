# Task: BMI 計算器 v3 — 三語版（繁中 / English / Bahasa Indonesia）/ 任務單

Date: 2026-10-12
From: Leader · Wailan (洄瀾)
To: Member · Taroko (太魯閣)

## What to do / 要做什麼

Take `workspace/outbox/20261012-bmi-calculator-v2.html` as the base and build **v3: a trilingual version**. All visible text must switch between three languages:

- **繁體中文（台灣）** — default on load
- **English**
- **Bahasa Indonesia（印尼文）**

## Format / 格式

- **One single self-contained HTML file** (`20261012-bmi-calculator-v3.html`) — CSS/JS inline, no external libraries, no internet needed.
- Add a **language switcher** at the top of the card: three buttons or a segmented control labelled `繁中` / `EN` / `ID` (or `中文` / `EN` / `ID`). Active language is highlighted.
- Switching language must instantly update: title, labels, placeholders, both buttons, error messages, result category name, tip text, and the 衛福部/reference table header & rows. `<html lang="...">` must update too (`zh-TW` / `en` / `id`).
- Implementation suggestion: a JS dictionary object with three keys, one `setLang(lang)` function that applies all strings. No page reload.

## Strings to translate / 要翻譯的字串

Suggested wording (polish as needed):

| Item | zh-TW | EN | ID |
|---|---|---|---|
| Title | BMI 計算器 | BMI Calculator | Kalkulator BMI |
| Height label | 身高（公分 / cm） | Height (cm) | Tinggi badan (cm) |
| Weight label | 體重（公斤 / kg） | Weight (kg) | Berat badan (kg) |
| Calculate button | 計算 | Calculate | Hitung |
| Reset button | 重設 | Reset | Ulangi |
| Result heading | 計算結果 | Result | Hasil perhitungan |
| Ref. table header | 衛福部 BMI 體位標準參考 | BMI categories (Ministry of Health standard) | Kategori BMI (standar Kemenkes) |
| 過輕 | 過輕 | Underweight | Kurang berat badan |
| 正常 | 正常 | Normal | Normal |
| 過重（微胖） | 過重（微胖） | Overweight | Kelebihan berat badan |
| 肥胖 | 肥胖 | Obesitas | Obesitas |
| Category boundaries | BMI < 18.5 / 18.5 ≤ BMI < 24 / … | same numbers | same numbers |

Error messages (4 cases × 2 fields) must also exist in all three languages, e.g.:
- 空白/非數字: 「請輸入數字（例如：170）」/ "Please enter a number (e.g. 170)" / "Masukkan angka (contoh: 170)"
- ≤0: 「數值必須大於 0」/ "Value must be greater than 0" / "Nilai harus lebih besar dari 0"
- 過小: 「數值過小，請確認單位是否為公分／公斤…」/ "Value too small, check that the unit is cm/kg" / "Nilai terlalu kecil, pastikan satuan dalam cm/kg"
- 太大: 「數值太大，請確認單位是否為公分／公斤…」/ "Value too large, check that the unit is cm/kg" / "Nilai terlalu besar, pastikan satuan dalam cm/kg"

Category tips (4 × 3 languages): translate the existing zh-TW advice into natural EN and ID — keep them short one-liners.

## What to keep / 要保留的

- Everything from v2: a11y attributes (`role="alert"`, `aria-live`, `aria-invalid`, focus handling), validation ranges (height 50–250, weight 10–300), colors, layout, Enter-to-calculate, reset behavior.
- After switching language, a previously shown result should either re-render in the new language or be cleared — no mixed-language leftovers.

## What "done" looks like / 怎樣算做完

1. New file in `workspace/outbox/` named `20261012-bmi-calculator-v3.html` — **v1 and v2 stay untouched**.
2. Load page → all zh-TW. Click `EN` → entire UI becomes English. Click `ID` → entire UI becomes Indonesian. No Simplified Chinese anywhere.
3. Error test in each language: enter height 400 → localized「數值太大…」/"Value too large…"/"Nilai terlalu besar…".
4. 170/65 still shows 22.5 → Normal/正常/Normal in the active language.
5. Still fully offline, single file, works with no network.
6. One handoff line in outbox: what you did, anything to watch, ready to use or not.

## Do not / 不要做

- Do not modify v1/v2 files; do not write into `workspace/shared/`; no external libraries or translation APIs.
