---
title: "Kadrey v. Meta Platforms, Inc."
alias: ["Meta Llama Books3 訴訟案", "Kadrey 案"]
filed_date: 2023-07-07
court: "U.S. District Court for the Northern District of California (N.D. Cal.)"
case_no: "3:23-cv-03417"
status: "Decided" # 2025年6月25日簡易判決 Meta 勝訴
modality: "Text & LLM"
target_entity: "Meta Platforms, Inc."
plaintiff: "Richard Kadrey 等 13 位作家"
core_issues:
  - "Fair Use (合理使用全面成立)"
  - "Piracy & Shadow Libraries (Books3 / LibGen)"
  - "End-to-End Transformative Purpose (端到端轉化性吸收)"
  - "Market Dilution (市場稀釋 / 間接市場替代)"
  - "Post-training Output Guardrails (五十字輸出限制)"
risk_level: "Medium"
slide_ready: true
---

# Kadrey v. Meta Platforms, Inc.

## 1. 案件基本概況 (Executive Overview)
- **一句話定調**：生成式 AI 模型商在美國聯邦法院取得的第一場全面性合理使用勝訴判決。法官認定 Meta 即使自影子圖書館下載 Books3 訓練 Llama 仍成立合理使用，但判決中首度深入闡述了「市場稀釋（Market Dilution）」之潛在威脅。
- **裁判日期與法官**：2025 年 6 月 25 日（僅在 Anthropic 裁定後兩天！），由同屬北加州聯邦地院之法官 Vince Chhabria 作成簡易判決（Summary Judgment），裁定 Meta 全勝。

---

## 2. 訴訟事實與技術對抗 (Factual Context)

- **資料集爭議**：Meta 訓練 Llama 系列時，因主流出版商拒絕授權或怠於回應，Meta 直接自影子圖書館下載 LibGen 及 Books3 資料集，總計包含原告 666 份著作副本。
- **後訓練技術防護 (Post-training Guardrails)**：
  - Meta 在完成預訓練後，對 Llama 執行了嚴格的後訓練對齊（Alignment）與記憶防護。
  - 原被告雙方專家證人在法庭測試中，**最多均只能誘導 Llama 輸出與原告著作相同之五十字以內片段**，無法原樣重現具實質意義之篇章。

---

## 3. 法官 Vince Chhabria 之核心判決論理

### 3.1 轉化性目的吸收前置下載（與 Anthropic 案之根本分歧）
- 法官 Chhabria 採取「端到端目的合併觀察」：
  - 下載行為雖涉及盜版書籍，但其最終目的係為訓練能夠創造全新表達之語言模型工具，而非轉售盜版書。
  - **行為人之主觀惡意不必然摧毀合理使用**：合理使用的宗旨是探求客觀利用是否創造新表達。只要最終用途具備高度轉化性，前置下載之瑕疵不影響第一要素之成立。

### 3.2 否定原告的「授權市場損害」主張
- 原告主張 Meta 侵害了其「授權他人訓練 AI 之授權金市場」。
- 法官直接駁回：**法律本來就未曾賦予著作權人壟斷「AI 訓練市場」之專屬權利**。如果只要假設理論上有授權市場存在就推論有損害，合理使用分析將淪為循環論證。

### 3.3 首度提出「市場稀釋 (Market Dilution)」概念
> [!IMPORTANT]
> **法官 Chhabria 留給未來版權方的訴訟武器：**
- 法院花費大量篇幅警告：AI 模型若以極低成本、無限量生成與人類作家相同文類之作品，將產生**「市場稀釋（Market Dilution / Indirect Substitution）」**，淹沒出版市場並摧毀人類創作者之經濟誘因。
- **Meta 本次為何能贏？** 原告律師在起訴狀與舉證中**完全沒有主張「市場稀釋」**，亦未提出實證銷量受損證據；反觀 Meta 提出了經濟學家與專家證詞證明短期內對原告銷量無可察覺之影響。

---

## 4. Anthropic 案 vs. Meta 案：兩大法官之世紀對比

| 爭點項目 | Bartz v. Anthropic (法官 Alsup) | Kadrey v. Meta (法官 Chhabria) |
| :--- | :--- | :--- |
| **下載影子圖書館** | ❌ **不成立合理使用**（獨立評價，不法性無法治癒） | ✅ **成立合理使用**（被訓練模型之最終轉化性吸收） |
| **人類閱讀類比** | 機器訓練如同人類學習，應享相同免費閱讀待遇。 | 反駁人類閱讀類比，強調模型學習統計關聯性是全新技術。 |
| **輸出記憶防護** | 模型未直接重製具表達性內容即可。 | 嚴格要求後訓練防護（五十字限制證明無直接替代）。 |
| **市場損害認定** | 認定影子圖書館實質替代出版購買。 | 否認直接授權市場損害，但警告「市場稀釋」之危險。 |

---

## 5. 簡報提煉模組 (Slide Ready Bullets)
- **指標大勝**：Meta 成功說服法官，即使自 Books3 下載小說訓練 Llama，仍因高度轉化性獲判合理使用。
- **安全防線關鍵**：Meta 的後訓練防護成功將記憶化輸出鎖死在「50 字以內」，成為免責定海神針。
- **未來伏筆**：法院警告「市場稀釋（大量 AI 產物淹沒人類市場）」將是未來擊破合理使用的真正死穴。
