> 交接：已完成 v3 三語版 BMI 計算器網頁（位於同目錄之 `20261012-bmi-calculator-v3.html`）；支援繁中／英文／印尼文即時切換、各語系完整錯誤訊息與無障礙規格，v1 及 v2 檔案完整保留；可直接以瀏覽器離線開啟使用。

# 成品回報：BMI 計算器 v3 — 三語版（繁中 / English / Bahasa Indonesia）

- 日期：2026-10-12
- 執行者：隊員・太魯閣 (Taroko)
- 對應任務：`workspace/inbox/20261012-bmi-app-v3-trilingual.md`
- 交付新版檔案：[`20261012-bmi-calculator-v3.html`](file:///c:/Users/user/Documents/Stuff%20for%20Intro%20to%20AI%20class/my-team/workspace/outbox/20261012-bmi-calculator-v3.html)
- 既有版本狀態：`20261012-bmi-calculator.html` (v1) 與 `20261012-bmi-calculator-v2.html` (v2) 完整保留未覆蓋。

## 完成項目檢驗

1. **三語即時切換（繁中／EN／ID）**：
   - 頂部設有分段語系切換按鈕（`繁中` / `EN` / `ID`），點擊即時更新，不需重整頁面。
   - 同步更新：`<html lang="...">` 標籤、頁面標題（`document.title`）、主標題、輸入欄位標籤與提示 placeholder、按鈕文字、衛福部標準參考表。
2. **計算結果與提示多語系同步**：
   - 四級體位（過輕 / 正常 / 過重（微胖） / 肥胖）在切換語言時即時更新對應文字與建議短語，無混雜語言殘留。
3. **錯誤訊息完整多語系支援（各 4 種情境）**：
   - 空白或非數字、≤0、過小（<50 cm / <10 kg）、過大（>250 cm / >300 kg）皆有繁中、英文、印尼文對應提示。
   - 若切換語言時畫面已有錯誤訊息，錯誤文字亦即時轉換為目標語系。
4. **完整保留 v2 無障礙與行為規範**：
   - 包含 `role="alert"`、`aria-live="polite"`、`aria-invalid`、錯誤時焦點自動返回第一項問題欄位。
   - 支援 Enter 鍵快速計算與重設（Reset）清理功能。
5. **完全離線單檔**：
   - 無任何外部字型、函式庫或網路 API 依賴。
