# 知識庫維護日誌 (Knowledge Base Activity Log)

> 本日誌記錄知識庫的所有重大操作（Ingest 來源消化、Research 檢索、Lint 校驗、Presentation 簡報編譯）。
> 遵循 Karpathy 規範格式：`## [YYYY-MM-DD] <操作類型> | <事件描述>`

---

## [2026-11-20] build-graph-presentation | 正式定案並實現「Graph 關係圖譜導向」教學專題簡報
- 依據確認之五階段工作流，正式完成【階段五：HTML / Reveal.js 實作編譯】：
  - 專屬檔案：`presentations/education/index.html`（共 10 頁核心投影片）
  - 全面採用「卡片節點（Structured Card Nodes）+ 箭頭關係鏈（Directional Edges）+ Hover 浮起微交互」
  - 核心偏向「教學實務優先」：
    1. 雙向發散拓撲：教學現場的 AI 雙刃劍
    2. 二元衝突圖：非營利教學 vs. 市場替代性迷思
    3. 外洩因果鏈：命題考卷被 AI 記憶並公開吐出的破口
    4. 實體矩陣：學生作業著作權與教師批量上傳個資隱私地雷
    5. 漏斗穿透圖：通道視野引發教師講義客觀侵權
    6. 惡性閉環圖：煞有介事之偽文獻辨識與認知外包
    7. 失衡天平圖：AI 偵測器 60% 誤判與母語歧視冤抑
    8. 雙盾牌架構：非合意法定授權與校園零保留沙盒（Zero Retention）
    9. 三大評量轉型：Prompt 思辨日誌、5 分鐘盲抽口試、逆向代碼審查
    10. 價值向心圖：終局思維收斂與批判力教育本質
  - 雙模態無縫切換：右上角維持「📄 切換至圖文講義手冊」按鈕，與 `handout.html` 雙向互通

## [2026-11-20] build-handout | 建立圖文講義手冊型 HTML 產物與雙模態導覽互通
- 編譯建立專屬圖文講義手冊：`presentations/education/handout.html`
  - 採用「瑞士國際主義風格 · 溫潤紙感淺色」排印系統（#f8f9fa 搭配高對比字體與克制冷灰藍）
  - 整合雙模態體驗：側邊固定章節目錄（Sticky TOC）、流程圖解、對比卡片、法規表格、評量轉型案例與教師 5 步自檢清單
  - 內建 `@media print` 專業排印樣式，支援瀏覽器 `Cmd+P` 一鍵列印或另存為 A4 PDF 實體講義
- 實現雙模態互通：
  - `presentations/education/index.html` 新增右上角懸浮按鈕「📄 切換至圖文講義手冊」
  - `presentations/education/handout.html` 頂部固釘導覽列提供「🖥️ 切換至投影片模式」
- 同步更新索引總目錄 `index.md`，納入圖文手冊條目與連結

## [2026-11-20] style-refactor | 全面升級為「瑞士國際主義風格 · 溫潤紙感淺色」簡約中性視覺體系
- 依據使用者需求確認，全面將 HTML 簡報重構為瑞士排印風格（Swiss International Typographic Style）
- 視覺規範定案：
  - 色彩基調：Substack/Notion 溫潤紙感淺灰白底（#f8f9fa），搭配純白卡片（#ffffff）與低視覺負擔深墨文字（#0f172a, #334155）
  - 字體排印：Inter 與 Noto Sans TC 嚴格無襯線格線排版，移除霓虹漸變，大留白與清晰層級
  - 輔助點綴：低彩度冷調藍（#2563eb）作為唯一主強調色，搭配柔和警示色（#dc2626, #d97706）
  - 結構組件：極簡實線卡片、無冗餘灰階表頭表格、經典側邊強調線 Callout 區塊
- 已同步重構：
  - `presentations/education/index.html`（教育專案簡報）
  - `presentations/index.html`（總合主簡報）

## [2026-11-20] build-presentation | 生成專題簡報與綜合分析：《LLM 在教學上的運用問題》
- 建立專題綜合分析頁面：`wiki/synthesis/llm-in-education.md`（完整解構教育合理使用迷思、教材試題洩漏、輸出端記憶化侵權、學術誠信、AI 探測器高偽陽性與評量轉型）
- 編譯建立專屬 Reveal.js HTML 簡報：`presentations/education/index.html`（共 10 頁投影片，採用自適應卡片、玻璃擬態暗色設計，支援離線全螢幕互動演講）
- 同步更新索引總目錄 `index.md`，納入教學專題條目與簡報連結

## [2026-11-20] ingest-paper | Sebastian Stober & Tim W. Dornis：《Generative AI Training and Copyright Law》（arXiv:2502.15858v2）
- 來源存入 `raw/papers/2026-03-generative-ai-training-and-copyright-law-stober-dornis-arxiv-2502-15858.md`
- 建立重大案例與訴訟頁面：
  - `wiki/cases/gema-v-openai.md`（德國慕尼黑第一地院 2025 年判決：GPT-4 歌詞記憶化侵權，全面破除歐盟 CDSM TDM 免責）
  - `wiki/cases/riaa-v-suno-udio.md`（唱片業巨頭訴 Suno/Udio 音樂生成：未授權商業母帶爬取、音色記憶化與合理使用答辯）
- 建立新興合規概念頁面：
  - `wiki/concepts/training-data-documentation.md`（三級文檔化框架：Tier 1 URL、Tier 2 ISRC/ISBN 標籤、Tier 3 AcoustID 聲學指紋，落實歐盟 AI 法第 53 條）
- 深度更新現有概念與理論體系：
  - `wiki/concepts/tdm-exceptions.md`（確立「GenAI 訓練非 TDM」核心理論定論，對照分析 TDM 與 GenAI 訓練之本質差異）
  - `wiki/concepts/memorization-leakage.md`（引入 Carlini 三要素、>50 tokens 通道視野效應、神經編解碼器代碼簿版權風險）
- 擴充橫向綜合分析：
  - `wiki/synthesis/timeline.md`（增補 2024 RIAA 訴訟、2025 GEMA 慕尼黑地院判決、2026 理論突破）
  - `wiki/synthesis/training-vs-output.md`（升級為輸入端、權重代碼簿、輸出端三層責任分析；警示學術 TDM 資料集轉商用之挪用陷阱）
- 擴充 Reveal.js 簡報：`presentations/index.html`（新增 GEMA 判決、RIAA 音樂 AI 戰役、神經編解碼器代碼簿風險、分級文檔化框架四大投影片）
- 同步更新索引總目錄 `index.md`

## [2026-11-20] ingest-paper | 蕭莉珍碩士論文：《生成式人工智慧之著作權侵權爭議與利益調和——非合意授權制度之規範模式初探》（指導教授：黃銘傑博士，臺大法律學系）
- 來源存入 `raw/papers/2026-07-copyright-infringement-interest-balance-gen-ai-non-voluntary-license-hsiao-ntu.md`
- 建立四大重要案例頁面：
  - `wiki/cases/bartz-v-anthropic.md`（Alsup 法官裁定紙本電子化合法、影子圖書館違法，15億美元和解）
  - `wiki/cases/kadrey-v-meta.md`（Chhabria 法官簡易判決 Meta 全勝，首度探討市場稀釋）
  - `wiki/cases/lawsnote-v-lawsource.md`（臺灣新北地院爬蟲重判 4 年、賠償 1.05 億元）
  - `wiki/cases/kneschke-v-laion.md`（德國漢堡地院裁定 LAION 科研豁免，自然語言 TOS 屬有效退出）
- 建立兩大深度概念頁面：
  - `wiki/concepts/non-voluntary-license.md`（責任法則、法定授權、階梯費率、限制退出權之本土規範建議）
  - `wiki/concepts/style-infringement.md`（風格侵權與思想表達二分、Steinberg 案細節表達門檻、吉卜力事件）
- 擴充橫向綜合分析：
  - `timeline.md`（增補第五階段：2025~2026 司法判決分野與法定授權倡議）
  - `risk-matrix.md`（納入影子圖書館 Books3 侵權死穴、臺灣爬蟲刑事責任風險）
- 擴充 Reveal.js 簡報：`presentations/index.html`（新增 2025 美國法院分水嶺、臺灣 Lawsnote 重判、非合意法定授權三大投影片）
- 同步更新索引總目錄 `index.md`

## [2026-11-20] ingest-paper | 葉奇鑫、許斌：《AI大語言模型訓練與著作權合理使用之思考——以紐約時報對OpenAI訴訟案為中心》
- 來源存入 `raw/papers/2024-06-ai-llm-training-copyright-fair-use-nyt-openai-yeh-hsu.md`
- 建立深度案例頁面：`wiki/cases/nyt-v-openai.md`（完整收錄訓練資料集佔比、100-token 逐字比對、雙方攻防與動議）
- 建立法規比較概念頁面：`wiki/concepts/tdm-exceptions.md`（歐盟 CDSM、英國、新加坡、日本與臺灣之 TDM 比較）
- 連動擴充概念頁面：`fair-use.md`（增補 Warhol 判決影響與我國第 65 條實務差異）、`memorization-leakage.md`（增補 RAG 與漏洞提示詞爭點）
- 擴充 Reveal.js 簡報：`presentations/index.html`（新增紐約時報案專頁與全球 TDM 規範對比頁）
- 同步更新索引總目錄 `index.md`

## [2026-11-20] build | 建立核心概念、橫向綜合架構與首版 Reveal.js 簡報
- 建立 `raw/cases/`、`raw/articles/`、`raw/papers/` 分流資料夾
- 建立三大綜合分析模組：`timeline.md`（時間線）、`training-vs-output.md`（雙軸分析）、`risk-matrix.md`（企業風險矩陣）
- 建立兩大核心法理與技術概念：`fair-use.md`（合理使用）、`memorization-leakage.md`（記憶化溢出）
- 編譯產出首版可離線互動之 Reveal.js HTML 簡報：`presentations/index.html`
- 同步更新索引總目錄 `index.md`

## [2026-11-20] config | 語言規則與論文下載管道設定
- 於 `Agent.md` 明定預設使用繁體中文，關鍵技術術語、模型名稱與法律專有名詞保留英文原文
- 建立 `raw/papers/` 專用目錄，配置「工作流 E：論文與外部來源接收」
- 支援對話上傳 PDF 保存與 arXiv 等外鏈自動下載 PDF 入庫

## [2026-11-20] init | 知識庫系統初始化
- 建立專案骨架目錄：`raw/`, `wiki/cases/`, `wiki/concepts/`, `wiki/synthesis/`, `presentations/`
- 配置標準化頁面範本：`case-template.md`, `concept-template.md`
- 訂定知識庫導覽總目錄 `index.md` 與操作日誌 `log.md`
- 撰寫生成式 AI 著作權專屬 `Agent.md` 規範指南
