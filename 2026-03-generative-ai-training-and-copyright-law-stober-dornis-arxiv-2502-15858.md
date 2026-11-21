# Generative AI Training and Copyright Law (生成式 AI 訓練與著作權法)

- **作者**：Sebastian Stober（德國馬德堡大學計算機科學系 AI 實驗室）、Tim W. Dornis（德國漢諾威大學法學院法律資訊學研究所所長）
- **文獻來源**：arXiv:2502.15858v2 [cs.CY]，2026 年 3 月 17 日（改編自作者 2024 年德文專書與 ISMIR 2024 特邀演講）
- **文獻收錄**：`raw/papers/2026-03-generative-ai-training-and-copyright-law-stober-dornis-arxiv-2502-15858.md`

---

## 核心綱要與跨領域重大突破

本論文係 AI 電腦科學家（Stober）與著作權法學權威（Dornis）深度合作之跨領域經典。全篇聚焦於**音樂資訊檢索（Music Information Retrieval, MIR）與多模態生成式 AI**，針對模型訓練、記憶化溢出、模型內部重製、以及歐盟與美國法制提出突破性定論。

### 1. 核心法律定論：生成式 AI 訓練本質上「不是 TDM」！
- **傳統 TDM**：旨在發現隱含規律、抽取事實資訊與統計趨勢（如音樂調性、拍速、情緒分類），不涉及原作之表達。
- **GenAI 訓練**：旨在擬合資料集之機率分佈，完整吸收並輸出具有原作風格、結構與實質表達之新作品，與原作構成直接市場競爭。
- **法律後果**：歐盟 CDSM 指令第 3、4 條 TDM 例外及各國 TDM 法規**均不適用於 GenAI 訓練**！模型商無權援引 TDM 作為免責金牌。

### 2. 模型記憶化（Memorization）之技術與法律剖析
- **嚴謹術語架構**：
  - **Memorization（記憶化）**：模型內部參數對訓練樣本的非結構化儲存（內部隱性機制）。
  - **Regurgitation（吐出 / 原樣重現）**：模型輸出端幾乎一字不差、像素級或音頻級重現訓練內容（可觀察的外在行為）。
  - **Memorization effects（記憶化效應）**：從細微特徵重複到原樣重現的光譜。
- **誘發三要素（Carlini 等，2023）**：模型參數規模、訓練資料重複頻率（Duplication）、提示詞上下文長度（>50 tokens 誘發穿透性「通道視野/Tunnel Vision」）。
- **重大判例實證**：德國慕尼黑第一地方法院（Landgericht München I，2025年11月11日，案號 42 O 14139/24）判決 GEMA 控告 OpenAI 案勝訴！認定 GPT-4/4o 記憶歌詞構成違法重製，明確駁回 TDM 抗辯。

### 3. 特別技術黑洞：神經音訊編解碼器（Neural Audio Codecs）
- 如 Meta EnCodec、Google Lyra、Descript Audio Codec。
- **法律定性**：神經編解碼器不是傳統 MP3 壓縮演算法，其權重包含由生成對抗或擴散模型習得的「Codebook（代碼簿）」。若解碼器輸出未包含在輸入碼流中的資訊，該資訊必然自權重中提取——因此**散布含有記憶化版權特徵的神經編解碼器權重模型，即構成散布侵權重製物！**

### 4. 落地工程解方：分級資料集文檔化框架（Tiered Documentation Framework）
- 針對歐盟 AI Act 第 53 條通用 AI「詳細資料摘要」與開源 AI（OSAID 1.0）要求，反對無實質意義的「開源洗白（Open-washing）」與「TDM 洗白（TDM-washing）」，提出三級文檔標準：
  - **Tier 1 (Basic)**：來源 URL、時間戳記、基礎檔案元數據。
  - **Tier 2 (Intermediate)**：嵌入 ISRC（國際標準錄音碼）、ISWC（國際標準音樂著作碼）唯一辨識碼。
  - **Tier 3 (Advanced)**：利用 MIR 音訊指紋（Audio Fingerprinting，如 AcoustID, MusicBrainz）對訓練資料進行逆向比對與透明化審計。
