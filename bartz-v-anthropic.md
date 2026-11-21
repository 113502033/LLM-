---
title: "Bartz v. Anthropic PBC"
alias: ["Anthropic 盜版書訓練訴訟案", "Bartz 案"]
filed_date: 2024-08-01
court: "U.S. District Court for the Northern District of California (N.D. Cal.)"
case_no: "3:24-cv-05417"
status: "Settled" # 2025年9月以15億美元天價達成和解
modality: "Text & LLM"
target_entity: "Anthropic PBC"
plaintiff: "Andrea Bartz, Charles Graeber, Kirk Wallace Johnson 等作家"
core_issues:
  - "Fair Use (合理使用)"
  - "Piracy & Shadow Libraries (影子圖書館 Books3 / LibGen 訓練)"
  - "Format Shifting (紙本書電子化格式轉換)"
  - "Central Training Database (中央資料庫長期儲存)"
risk_level: "High"
slide_ready: true
---

# Bartz v. Anthropic PBC

## 1. 案件基本概況 (Executive Overview)
- **一句話定調**：生成式 AI 著作權史上賠償規模最大的指標判決與和解案。法院劃出了「合法自購紙本書電子化 vs. 影子圖書館盜版下載」的合理使用生死線，最終促成 15 億美元的天價和解。
- **裁判與結果**：2025 年 6 月 23 日，聯邦法官 William Alsup 作成中間裁定（Summary Judgment Order）；同年 9 月，Anthropic 同意支付 15 億美元（針對近 50 萬本受保護著作，每本賠償 3,000 美元）與原告達成歷史性和解。

---

## 2. 訴訟事實與資料集來源 (Data Pipeline Facts)

Anthropic 開發聊天機器人 Claude 所建立的「中央資料庫」包含兩種完全不同性質的資料來源：
1. **合法收購紙本書電子化（Format Shifting）**：
   - 向出版商購買大量紙本書，拆裝逐頁高解析度掃描為電子檔，並銷毀紙本書，僅保留單一電子副本。
2. **影子圖書館盜版下載（Piracy Ingestion）**：
   - 直接從 Books3、Library Genesis (LibGen)、Pirate Library Mirror 等盜版網站批次下載數億份未經授權之電子書掃描檔。

---

## 3. 法官 William Alsup 的劃時代裁定：雙重標準

法官 Alsup 將 Anthropic 的著作利用拆解為三大行為，並得出截然不同的合法性評價：

| 評估行為態樣 | 裁判結果 | 法院核心論理 |
| :--- | :---: | :--- |
| **1. 訓練大型語言模型 (LLM Training)** | ✅ **成立合理使用** | 訓練模型係為創造新文本，具高度轉化性；類比人類讀者博覽群書學習文法風格，機器亦不應被要求回顧記憶每次付費；模型輸出端並未直接重製具表達性內容。 |
| **2. 自購紙本書掃描建置資料庫** | ✅ **成立合理使用** | 屬於合法形式轉換（Format Shifting），有助於節省空間與檢索便利；且紙本已銷毀僅保留一份電子檔，未向公眾散布，對潛在市場影響中立。 |
| **3. 自影子圖書館下載建置資料庫** | ❌ **不成立合理使用** | **惡意侵權！** 被告本可合法購書卻捨正道而下載盜版，行為欠缺正當性；後續模型訓練的轉化性無法「治癒」前置下載行為的不法，且永久儲存對出版市場造成實質替代。 |

---

## 4. 產業與合規啟示 (Enterprise Takeaways)
> [!CAUTION]
> **給 AI 開發商與企業法務的血淚教訓：**
1. **「轉化性使用」不能清洗資料來源的非法性**：
   - 法院明確否定「後續拿去訓練 LLM 很偉大，就能回溯豁免前置下載盜版罪行」的抗辯。
2. **影子圖書館（Books3, LibGen 等）是致命雷區**：
   - 任何商業模型的訓練管線中若包含 Books3 或未經授權的爬蟲庫，均將面臨法定損害賠償與集體訴訟破產風險。
3. **格式轉換（Format Shifting）的防禦有效性**：
   - 企業若合法採購實體版權物並依比例原則進行內部數位化分析（且確實銷毀或封存實體），能獲得法院相當程度之保護。

---

## 5. 簡報提煉模組 (Slide Ready Bullets)
- **歷史天價**：Anthropic 支付 15 億美元和解金，創下 AI 產業著作權賠償紀錄。
- **司法分界嶺**：合法購書電子化訓練被判合理使用；但自影子圖書館（Books3/LibGen）抓取盜版直接宣告侵權！
- **法理警鐘**：模型的創新轉化性，無法「漂白」前置資料蒐集階段的盜版不法性。
