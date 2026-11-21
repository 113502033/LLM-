---
title: "訓練資料集分級文檔化框架 (Tiered Documentation Framework)"
category: "Engineering Compliance & Legal Standards"
related_jurisdictions: ["EU", "US", "Global"]
slide_ready: true
---

# 訓練資料集分級文檔化框架 (Tiered Documentation Framework)

## 1. 概念背景與迫切需求 (Context & Urgency)

隨著各國監管法規收緊與跨國侵權訴訟爆發，「黑盒化」的訓練資料蒐集方式已成為 AI 企業最致命的法律隱患。
- **歐盟 AI 法案（EU AI Act）第 53 條第 1 項 (d) 款**：強制要求通用 AI（GPAI）模型提供商必須公開發布其預訓練資料內容之「充分詳細摘要（Sufficiently Detailed Summary）」。
- **開源 AI 定義（OSAID 1.0）**：開源促進會（OSI）於 2024 年底定案的標準亦明定，唯有提供訓練資料的完整來源清單與審計資訊，模型方能被冠以「開源（Open Source）」之名。
- **杜絕「洗白現象」**：
  - **開源洗白（Open-washing）**：僅開放模型權重，卻將訓練資料來源列為商業機密，迴避法律審查。
  - **探勘洗白（TDM-washing）**：將大規模爬取版權著作混充為「合法文字與數據探勘」，拒絕提供作品清單。

為解決模型開發商「保護商業機密」與權利人「確認著作權保留（Opt-out）」之間的僵局，計算機科學家 Sebastian Stober 與法學教授 Tim W. Dornis 於 2026 年提出了**分級文檔化框架（Tiered Documentation Framework）**。

---

## 2. 三級文檔化架構 (The 3-Tier Architecture)

```
┌────────────────────────────────────────────────────────┐
│ Tier 3: 音訊/感知指紋比對 (Acoustic & Perceptual Fingerprint) │  <- 司法鑑識級
│         (AcoustID, Chromaprint, MusicBrainz, pHash)    │
├────────────────────────────────────────────────────────┤
│ Tier 2: 國際標準元數據標識碼 (Standard Work Identifiers)   │  <- 版權媒合級
│         (ISRC, ISWC, ISBN, DOI)                        │
├────────────────────────────────────────────────────────┤
│ Tier 1: 基礎網路爬取元數據 (Basic Metadata & URLs)          │  <- 基本透明度
│         (URLs, Timestamps, Domain Ratios, File Headers)│
└────────────────────────────────────────────────────────┘
```

### Tier 1：基礎網路元數據（Basic Metadata）
- **文檔內容**：抓取來源的 URL 網址、抓取時間戳記、網路域名分佈比例、檔案格式標籤、Token 或樣本總數。
- **適用場景**：滿足最基本的公開透明度要求（如 Common Crawl 基本統計）。
- **局限性**：無法有效讓版權人核對個別著作是否被攝入，亦無法防止洗掉元數據的盜版音訊混入。

### Tier 2：國際標準識別碼（Standard Content Identifiers）
- **文檔內容**：整合出版、音樂與影視產業成熟的全球通用識別標籤：
  - **音樂音訊**：**ISRC**（國際標準錄音碼，標識特定錄音版本）、**ISWC**（國際標準音樂著作碼，標識詞曲創作）。
  - **文字圖書**：**ISBN**（國際標準書號）、**DOI**（數位物件識別碼）、**ISSN**（期刊號）。
- **法規價值**：能與著作權集體管理組織（CMO，如 GEMA、MUST、ASCAP）的資料庫進行全自動 API 媒合，作為非合意授權或分潤結算的精確依據。

### Tier 3：音訊/感知指紋與特徵雜湊（Forensic Fingerprinting & Perceptual Hashing）
- **文檔內容**：
  - **音訊/音樂**：利用聲音物理頻譜生成的**聲學指紋**（如 **AcoustID / Chromaprint**、MusicBrainz 聲學指紋、Dejavu 演算法）。
  - **影像/多模態**：感知雜湊（Perceptual Hash, pHash / dHash）與多模態特徵嵌入向量雜湊（Feature Embedding Hashes）。
- **破除黑盒的最強武器**：
  - 即使爬蟲抓取的是被抹除 ID3 標籤的盜版 MP3、或是經過二次轉碼的 YouTube 側錄音訊，Tier 3 指紋比對仍可在數毫秒內以高達 99.9% 準確度鎖定原始母帶。
  - **兼顧商業機密與法律審查**：模型商無須公開未經授權的原始音檔或文字，僅需公開指紋雜湊表（Hash Tables），即可由獨立第三方審計機構或法院快速判定是否包含原告著作。

---

## 3. 對著作權保留（Opt-out）機制的技術賦能

歐盟 CDSM 指令第 4 條第 3 項允許權利人以「機器可讀方式（Machine-readable manner）」明示保留權利（Opt-out）。然而在缺乏分級文檔的情況下，權利人根本無法證明 AI 開發商「已接觸並無視」該保留聲明。

透過分級文檔化框架：
1. **事前過濾（Pre-training Filtering）**：抓取爬蟲在建置資料集時，比對 Tier 2 識別碼與 Tier 3 指紋庫中已登記 Opt-out 的作品，實施前置封鎖。
2. **事後舉證（Post-hoc Auditing）**：在訴訟中，原告可直接提供其作品的 ISRC 或 AcoustID 指紋，交由法院於模型資料庫雜湊表中檢索，一秒判定侵權接觸事實。

---

## 4. 企業與研發團隊落地實踐手冊 (Implementation Playbook)

| 階段 | 工程落實要點 | 法律合規效益 |
| :--- | :--- | :--- |
| **資料抓取階段** | 完整記錄 HTTP Headers、URL 來源、網頁 robots.txt 授權宣告與時間戳記（Tier 1）。 | 排除主觀惡意，證明善意採集與初步合規。 |
| **資料清洗階段** | 保留並提取多媒體檔案內嵌之 EXIF、ID3、ISRC、DOI 等元數據，建立索引庫（Tier 2）。 | 便於未來對接集體授權機構或進行合法授權補償。 |
| **入庫訓練前** | 對所有音訊、影像資料批次計算 AcoustID / pHash 指紋，與已知盜版資料庫（如 Books3、LibGen 雜湊）執行碰撞剔除（Tier 3）。 | 徹底阻絕模型記憶化風險，防範被判處懲罰性法定賠償。 |

---

## 5. 簡報提煉模組 (Slide Ready Bullets)

- **告別黑盒訓練**：歐盟 AI 法第 53 條強制要求通用 AI 模型公開訓練資料詳細摘要。
- **三級透明化框架**：Tier 1 (基礎 URL)、Tier 2 (ISRC/ISBN 國際標準碼)、Tier 3 (音訊指紋 AcoustID/pHash)。
- **破解開源洗白**：反對「只開權重不開資料」的假開源，建立具備鑑識力的資料集審計標準。
- **指紋比對秒殺盜版**：抹除標籤的側錄音訊，透過 Tier 3 聲學指紋亦能在毫秒內被精確鎖定。
