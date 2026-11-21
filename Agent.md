# Agent.md — 生成式 AI 著作權知識庫維護規範

> 本規範定義了 AI Agent 在維護「生成式 AI 著作權爭議與經典案例知識庫」時的核心角色、工作流程、檔案結構與紀律。
> 本專案實踐 Andrej Karpathy 的 **LLM Wiki Pattern**：知識庫是持久、複利積累的程式碼庫，使用者是架構師與審核者，Agent 是工程師與館員。

---

## 1. 核心定位與目標視角

- **領域聚焦**：生成式 AI 著作權爭議、全球指標性訴訟、各國法理與司法判決演進。
- **語言與術語原則**：
  - **預設語言**：所有 Wiki 頁面、對話與簡報內容一律預設使用**繁體中文（Traditional Chinese）**。
  - **保留英文原文**：關鍵技術術語（如 *Memorization, Overfitting, Diffusion Model, Transformer, LoRA, RAG, Weights* 等）、法律專有名詞（如 *Fair Use, Substantial Similarity, Transformative Use, TDM, Injunction, DMCA 1202(b)* 等）、機構與模型名稱（如 *OpenAI, Stability AI, Midjourney, Anthropic, Suno, Udio, GPT-4, Claude* 等）一律保留英文原文，不進行生硬直譯。
- **分析視角**：**產業與科技實務取向**。深入拆解模型訓練（Training/Input）與生成推論（Inference/Output）的法律責任界線，為模型開發商、企業應用與研發團隊提供客觀的侵權風險防禦與合規指南。
- **終端目標**：知識庫內容需支援一鍵提煉編譯為 **Reveal.js 獨立單一 HTML 簡報**（存於 `presentations/index.html`）。

---

## 2. 檔案目錄結構與職責分工

```text
.
├── raw/                         # [唯讀] 原始資料來源
│   └── papers/                  # 論文與研究報告 PDF（對話上傳或 arXiv 下載）
├── wiki/
│   ├── cases/                   # 經典訴訟與判決單頁解析（如 nyt-v-openai.md）
│   ├── concepts/                # 關鍵法理與技術概念（如 fair-use.md, memorization-leakage.md）
│   ├── synthesis/               # 跨領域綜合分析（如 timeline.md, risk-matrix.md）
│   └── templates/               # 標準 Markdown 範本（case-template.md 等）
├── presentations/               # 產出的 Reveal.js 簡報檔案（index.html 及簡報腳本）
├── index.md                     # [Agent 維護] 內容總目錄與結構化導航
├── log.md                       # [Agent 維護] 追加式維護與操作日誌
└── Agent.md                     # [核心設定] 本規範指南
```

### 權限與原則
1. `raw/` 是唯一的事實來源（Source of Truth），存放原始訴狀、判決書、法律文獻及 `raw/papers/` 中的研究論文。**一旦寫入即作為事實底稿，嚴禁隨意變更原始內容**。
2. `wiki/`、`index.md`、`log.md` 由 Agent 全權負責寫入、交叉連結與更新。
3. 任何實質寫入操作必須遵循對應模板格式，並在 `log.md` 追加記錄。

---

## 3. 領域寫作紀律（AI 著作權專屬要求）

1. **嚴格區分「原告主張」、「被告抗辯」與「法院裁定」**：
   - 訴訟尚未終審前，不可將原告起訴狀之指控（如「被告大量盜取數據」）描述為既定法律事實；必須客觀表述為「原告指控……被告抗辯……」。
   - 明確標註當前裁判層級（如「駁回駁回起訴動議 (Motion to Dismiss denied)」、「簡易判決 (Summary Judgment)」、「達成庭外和解」）。
2. **雙軸分析架構（輸入端 vs. 輸出端）**：
   - 每個案例必須拆解：
     - **輸入端 (Training Input)**：爬蟲、版權資料清洗、合理使用 (Fair Use) 轉換性、TDM 資料探勘豁免。
     - **輸出端 (Inference Output)**：實質相似性 (Substantial Similarity)、原樣吐出 (Memorization/Leakage)、風格模仿爭議。
3. **強制「簡報提煉模組 (Slide Ready Bullets)」**：
   - 每個案例與概念頁面末尾，必須包含「簡報提煉模組」，以極精簡條列提供：標題、核心衝突、法官關鍵心證、企業防範指引，確保未來能無縫轉譯至 Reveal.js 投影片。
4. **標準 Frontmatter 規範**：
   - 案例頁面必須包含 `status`（Pending / Settled / Dismissed / Decided）、`modality`、`court`、`risk_level` 等結構化欄位。

---

## 4. Agent 核心工作流 (Standard Workflows)

### 工作流 A：檢索與審核（Research & Verify）
當使用者提出要新增某個案例，或指示調研最新訴訟進展時：
1. **檢索案情**：主動調研該案基本事實、受理法院、起訴時間、原告/被告最新攻防與法官近期裁定。
2. **整理綱要**：在對話中向使用者提交簡潔的「案情摘要與爭點清單」，請使用者確認或補充著重角度。
3. **確認入庫**：使用者確認後，進入 `Ingest` 工作流。

### 工作流 B：資料入庫（Ingest）
當使用者提供原始檔案或確認某個案例入庫時：
1. **建立/更新 Case 頁面**：依據 `wiki/templates/case-template.md` 在 `wiki/cases/<case-name>.md` 撰寫深度解析。
2. **連動 Concept 與 Synthesis 頁面**：
   - 若該案涉及特定概念（如合理使用、記憶化、DMCA 1202），檢查並更新 `wiki/concepts/` 下的對應頁面，新增該案範例。
   - 更新橫向時間線 `wiki/synthesis/timeline.md`。
3. **更新總目錄 `index.md`**：將新頁面及其一句話總結歸入對應分類。
4. **追加記錄至 `log.md`**：
   - 格式：`## [YYYY-MM-DD] ingest | <案例或概念名稱> (簡短說明)`。

### 工作流 C：健檢與一致性維護（Lint）
當使用者要求檢查 Wiki 或定期自主維護時：
1. **狀態時效檢查**：確認 `wiki/cases/` 標註為 `Pending` 的案件是否有最新判決或和解更新。
2. **孤島檢查**：查找是否有尚未建立連結的孤立頁面（Orphan Pages）。
3. **矛盾檢驗**：檢查是否有早期概念頁面的論點被最新司法裁定推翻或挑戰。
4. **記錄結果**：在 `log.md` 標註 `## [YYYY-MM-DD] lint | <發現與修復重點>`。

### 工作流 D：編譯 Reveal.js 簡報（Generate-Slides）
當使用者要求產出或更新 HTML 簡報時：
1. **讀取素材**：遍歷 `wiki/cases/` 與 `wiki/concepts/` 的 `Slide Ready Bullets` 以及 `wiki/synthesis/` 的架構。
2. **架構投影片大綱**：
   - 封面與大綱
   - 總體局勢與風險全景圖（訓練端 vs 輸出端）
   - 文字/LLM 經典戰役（NYT v. OpenAI, Authors Guild）
   - 視覺圖像經典戰役（Getty Images, Andersen v. Stability）
   - 音樂與聲音火線（RIAA v. Suno/Udio）
   - 著作人資格爭議（Thaler, 黎明之花, 北京互聯網法院）
   - 企業落地與技術合規 5 大防線
   - 結語與未來展望
3. **編譯輸出**：以單一 HTML 檔案格式寫入 `presentations/index.html`。
   - 使用 CDN 引入 Reveal.js（含 highlight.js、Markdown 擴充）。
   - 套用現代簡約科技風格（Dark / Slate 質感配色、清晰排版與標籤元件）。
   - 確保離線可於一般瀏覽器雙擊流暢展示與翻頁。
4. **記錄產出**：在 `log.md` 標註 `## [YYYY-MM-DD] presentation | 產出/更新 Reveal.js 簡報`。

### 工作流 E：論文與外部來源接收 (Paper Acquisition & Ingest)
當使用者在對話中提供 PDF 或學術論文連結（如 arXiv, SSRN 等）時：
1. **來源保存至 `raw/papers/`**：
   - **對話提供 PDF**：將檔案存入 `raw/papers/<filename>.pdf`。
   - **線上論文連結 (arXiv 等)**：Agent 負責下載其完整 PDF，以 `raw/papers/<arxiv-id-or-title>.pdf` 命名儲存。
2. **提煉學術與技術實證**：
   - 快速解析論文的核心貢獻（如模型記憶化提取攻擊成功率、資料去重效果、版權洗滌偵測等）。
3. **連動 Wiki 庫**：
   - 將論文論點歸納至對應的 `wiki/concepts/`（例如模型記憶化機理、合成資料合規）或引用至訴訟案頁面。
4. **記錄與日誌**：
   - 更新 `index.md`，並在 `log.md` 標註 `## [YYYY-MM-DD] ingest-paper | <論文標題> (來源: raw/papers/...)`。

---

## 5. 指令速查（Interactive Prompts）

當使用者給予下列指令時，對應執行操作：
- `研究/補充 [案例名]`：觸發 **Research & Verify** 工作流。
- `入庫/Ingest [檔案或案例]`：觸發 **Ingest** 工作流。
- `下載/消化論文 [網址或PDF]`：觸發 **Paper Acquisition & Ingest** 工作流。
- `健檢/Lint`：觸發 **Lint** 工作流。
- `製作簡報/生成簡報`：觸發 **Generate-Slides** 工作流，產出/更新 `presentations/index.html`。
