---
title: "The New York Times Company v. Microsoft Corporation & OpenAI"
alias: ["NYT v. OpenAI", "紐約時報訴 OpenAI 與微軟案"]
filed_date: 2023-12-27
court: "U.S. District Court for the Southern District of New York (S.D.N.Y.)"
case_no: "1:23-cv-11195"
status: "Pending" # 進入證據開示程序 (Discovery)
modality: "Text & Multi-modal"
target_entity: ["OpenAI", "Microsoft"]
plaintiff: "The New York Times Company"
core_issues:
  - "Fair Use (合理使用)"
  - "Transformative Use (轉化性利用)"
  - "Memorization & Leakage (模型記憶化原樣重現)"
  - "Contributory Infringement (幫助侵權)"
  - "DMCA 1202(b) (移除著作權管理資訊)"
  - "Synthetic Search Results (合成搜尋結果替代效應)"
risk_level: "High"
slide_ready: true
---

# The New York Times v. OpenAI & Microsoft

## 1. 案件基本概況 (Executive Overview)
- **一句話定調**：生成式 AI 發展史上最具指標性的著作權訴訟，原告以翔實的資料集佔比與數百個模型逐字洩漏證據，全面挑戰「模型訓練屬於合理使用」之技術神話。
- **當前訴訟進展**：截至 2024 年中，雙方針對部分駁回動議（Partial Motion to Dismiss）進行攻防後，法院已排定案件管理期程，正式進入大規模證據開示（Discovery）實質審理階段。

---

## 2. 訴訟核心數據與技術事實 (Technical Facts & Datasets)

依據起訴狀與 OpenAI 公開文件，紐約時報作品在 GPT 系列訓練集中佔據極高權重：

| 訓練資料集 | 模型代數 | 紐約時報作品之權重與規模 |
| :--- | :--- | :--- |
| **WebText** | GPT-2 (2019) | NYTimes.com 為資料集中前 15 個域名之一，排第 5 個頂級域名，文本達 333,160 項。 |
| **Common Crawl** | GPT-3 / GPT-4 | 抓取量**排名第一的專有權利保護域名**（各類域名總量排第三，僅次於維基百科與 Google 專利庫），包含超 6600 萬份文件紀錄。 |
| **WebText2** | GPT-3.5 / GPT-4 | OpenAI 承認之高品質資料集，含紐約時報 20 多萬筆 URL，佔總量 1.23%。 |

---

## 3. 訴訟核心爭點 (Core Disputes)

### 3.1 輸入端爭議 (Training / Ingestion Phase)
- **非授權海量重製**：原告推估數百萬篇具版權保護之報導被未經授權爬取、分割、標籤化並存入訓練記憶庫。
- **繞過付費牆 (Paywall Bypass)**：原告設有收費訂閱機制，被告爬蟲在未付費狀況下抓取內部深度報導。
- **非消費性使用辯護 (Non-consumptive Use)**：被告援引 *Google Books* 與 *Oracle* 案，主張訓練並非販售新聞重製物，而是學習語言語法結構與統計規律，具有極高的轉化性（Transformative）。

### 3.2 輸出端爭議 (Inference / Generation Phase)
- **模型記憶化洩漏 (Memorization Leakage)**：
  - 原告舉證 GPT-4 在特定 Prompt 提示下，能夠一字不差（逐字輸出達數百字）重現紐約時報獲普立茲獎之深度調查報導（如紐約計程車牌照剝削案調查）。
- **微軟 Bing 合成搜尋結果 (Synthetic Search Results)**：
  - 結合 GPT 的 Bing Chat 能夠在搜尋結果中直接整合並完整引述紐約時報內容，使用者無須點擊原始連結即可獲取全文資訊，造成「零點擊（Zero-click）」，實質剝奪網站流量與訂閱商業利益。

---

## 4. 雙方主張與法律攻防 (Claims & Defenses)

| 爭端維度 | 原告紐約時報主張 (Plaintiff) | 被告 OpenAI & 微軟抗辯 (Defendant) |
| :--- | :--- | :--- |
| **直接侵權<br>(17 U.S.C. § 501)** | 爬取未授權付費內容訓練模型；輸出端產生一字不差之複製品與衍生著作。 | 訓練屬非消費性合理使用；3 年前的早期訓練已罹於訴訟時效（17 U.S.C. § 507(b)）。 |
| **記憶化輸出** | 模型並非抽象學習，而是具體儲存並洩漏受保護著作。 | 原告使用高度誘導性、對抗式 Prompt 經過上萬次嘗試觸發的模型漏洞，非一般使用者常態。 |
| **幫助侵權** | 微軟提供超級運算基礎設施、Browse with Bing 插件，明知並協助侵權。 | 原告未具體說明被告如何「知悉」個別終端使用者的侵權行為，起訴無充分事實支持。 |
| **DMCA 1202(b)** | 在訓練與合成搜尋過程中故意移除著作權管理資訊（CMI）與作者標籤。 | 內部訓練無散布行為；原告未舉證 CMI 遭移除造成何種具體實質損害。 |
| **合理使用** | 商業性質濃烈，輸出具同質性與功能性替代，不具轉換性。 | 符合新技術創新的合理使用前例（如家庭錄影機、搜尋引擎快照、API 轉換）。 |

---

## 5. 法理深入：後 Warhol 時代的 Fair Use 危機

葉奇鑫律師與許斌博士論文指出，本案不同於過往 *Google Books* 判決的兩大硬傷：
1. **Google Books 的有限節錄 vs. LLM 的全文替代**：
   - *Google Books* 當年勝訴在於「僅提供有限片段預覽（Snippets）」，反而促進了實體書籍的推廣，不具市場替代性。
   - LLM 產出內容在功能上高度重疊，使用者直接獲取答案後即不再前往紐約時報官網。
2. **美國最高法院 *Goldsmith (2023)* 判決的門檻提高**：
   - 最高法院收緊了「轉換性利用」認定：若被告利用目的與原著作之目的相同（皆提供新聞資訊），且具商業營利屬性，難以再僅憑形式技術創新成立合理使用。

---

## 6. 比較法視角（非美國法之審視）

根據論文分析，若本案置於其他主要法域，被告抗辯面臨更嚴峻挑戰：

- **歐盟（EU CDSM 指令 & AI Act）**：
  - CDSM 第 4 條 TDM 例外以「合法存取」為前提；繞過 Paywall 難認合法。
  - TDM 僅豁免「重製權」，不及於輸出端之改作與向公眾傳播。
  - AI Act 明定通用型 AI 必須揭露訓練集摘要並遵守著作權人保留聲明。
- **英國（UK CDPA § 29A）**：
  - 資料探勘例外明文僅限於「非商業科學研究」，商業性 LLM 訓練直接被排除。
- **新加坡（Copyright Act 2021 § 244）**：
  - 運算資料分析例外雖允許商業分析，但仍受制於合法存取要件，且目的限於運算研究，不涵蓋 LLM 的商業替代性服務。
- **臺灣（著作權法第 65 條第 2 項）**：
  - 我國司法實務尚未系統化承認美式「轉換性使用」作為壓倒性抗辯；法院審查商業目的、質量龐大、存在實質市場替代效應下，**紐約時報在臺灣勝訴的機率可能比在美國更高！**

---

## 7. 企業與模型開發商合規啟示 (Enterprise Takeaways)
> [!IMPORTANT]
> **本案給企業落地與自建 LLM 的核心教訓：**
1. **嚴禁將未付費授權之商業付費牆 (Paywall) 內容放入訓練集**：合法存取權（Lawful Access）是全球所有資料探勘免責的底線。
2. **消解模型記憶化是第一要務**：如果輸出端被舉證出實質原樣輸出，法官極可能直接推定訓練端具有直接侵權之實質關聯。
3. **RAG 與合成搜尋之引用規範**：若透過 RAG 即時檢索外部文章，必須保留著作權標記，且應引導使用者點擊原文，避免輸出覆蓋度過高的全文摘要。

---

## 8. 簡報提煉模組 (Slide Ready Bullets)
- **案件地位**：生成式 AI 版權史上第一大戰，原告以紮實數據證明紐約時報是 Common Crawl 排名第一的專有域名。
- **核心漏洞**：GPT-4 逐字重現普立茲報導（Memorization），成為擊穿合理使用防線的最致命證據。
- **司法變數**：美國最高法院 *Goldsmith* 判決收緊轉換性門檻，商業競爭與市場替代將主導陪審團判斷。
- **跨國啟示**：在歐盟、英國及臺灣法制下，商業 AI 訓練更難主張免責，促使科技巨頭加速走向「付費版權授權協議」。

---

## 9. 關聯索引 (Cross References)
- **基礎文獻**：[葉奇鑫、許斌：《AI大語言模型訓練與著作權合理使用之思考——以紐約時報對OpenAI訴訟案為中心》](file:///Users/wuyan-xi/Downloads/LLM%20Wiki%20Notes/raw/papers/2024-06-ai-llm-training-copyright-fair-use-nyt-openai-yeh-hsu.md)
- **關聯概念**：
  - [[wiki/concepts/fair-use.md]]（合理使用四要素與後 Warhol 危機）
  - [[wiki/concepts/memorization-leakage.md]]（模型記憶化與對抗式 Prompt 攻防）
  - [[wiki/concepts/tdm-exceptions.md]]（各國文字與資料探勘法制比較）
- **關聯分析**：
  - [[wiki/synthesis/training-vs-output.md]]（雙軸責任模型）
  - [[wiki/synthesis/timeline.md]]（訴訟時間線）
