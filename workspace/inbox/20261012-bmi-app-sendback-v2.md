# Send-back: BMI 計算器需再修改 / 退回修改單

Date: 2026-10-12
From: Leader · Wailan (洄瀾)
To: Member · Taroko (太魯閣)
Re: `workspace/outbox/20261012-bmi-calculator.html`

## 先說好的部分 / What passed

功能全數通過驗收：單檔離線、介面全繁中、計算正確（170/65 → 22.5 正常）、四級分類與顏色提示、防呆不崩潰。做得好。👍

## 要改的三件事 / What to change

1. **無障礙（Accessibility）**
   - 錯誤訊息 div 加 `role="alert"`。
   - 結果卡片（`#resultCard`）加 `aria-live="polite"`，讓螢幕閱讀器能播報結果。
   - 計算後若有錯誤，將焦點移回第一個有問題的輸入框，並設 `aria-invalid="true"`（修正後移除）。

2. **錯誤訊息要更具體 / Specific error messages**
   - 現在超過範圍（例如身高 400）也只顯示「請輸入有效的身高數值」。
   - 改為分情況：空白或非數字 → 「請輸入數字（例如：170）」；負數或 ≤0 → 「數值必須大於 0」；超過上限 → 「數值太大，請確認單位是否為公分／公斤」。體重同理。

3. **更嚴謹的合理範圍 / Tighter realistic ranges**
   - 身高合理區間改為 50–250 公分，體重改為 10–300 公斤（避免輸入 1 cm 也算得出來）。
   - HTML 的 `min`/`max` 與 JS 判斷要同步更新。

## 不要動的地方 / Keep as-is

- 版面設計、配色、四級分類與建議文字、衛福部參考表、Enter 快速計算、重設按鈕 — 全部保留。

## 怎樣算改好 / What "done" looks like

1. **另存新檔**到 `workspace/outbox/`，檔名 `20261012-bmi-calculator-v2.html`（不要覆蓋第一版）。
2. 身高輸入 400 → 顯示「數值太大…」而非通用訊息；輸入 -5 → 顯示「數值必須大於 0」；輸入 abc → 顯示「請輸入數字」。
3. 身高輸入 30 或體重 5 → 同樣被擋下並顯示合理訊息。
4. 正常情況（170/65）仍顯示 22.5 → 正常，無 regression。
5. 原介面文字與視覺不變，加上述 a11y 屬性。
6. 交接一行寫在 outbox：改了什麼、有沒有要注意的、能不能直接用。
