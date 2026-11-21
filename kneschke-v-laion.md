---
title: "Robert Kneschke v. LAION e.V."
alias: ["LAION 德國漢堡法院資料探勘案", "Kneschke 案"]
filed_date: 2023-04-01
court: "德國漢堡地方法院 (Landgericht Hamburg, Case No. 310 O 227/23)"
status: "Decided" # 2024年判決 LAION 勝訴（原告上訴中）
modality: "Image & Multimodal"
target_entity: "LAION e.V. (非營利組織)"
plaintiff: "Robert Kneschke (德國攝影師)"
core_issues:
  - "TDM Exception for Scientific Research (歐盟 CDSM 第 3 條 / 德著第 60d 條)"
  - "Machine-readable Opt-out (機器可讀保留聲明解釋)"
  - "Data Laundering (非營利組織建置資料庫之「資料洗錢」疑慮)"
  - "Lawful Access (合法存取免費帶浮水印預覽圖)"
risk_level: "Medium"
slide_ready: true
---

# Robert Kneschke v. LAION e.V.

## 1. 案件基本概況 (Executive Overview)
- **一句話定調**：歐盟境內第一起針對生成式 AI 訓練資料集建置適用「歐盟 CDSM 指令」的判例。法院認定非營利組織建置 LAION 資料集屬於「科學研究目的之資料探勘」，宣告免責；但附帶意見指出自然語言使用條款亦可構成有效的機器可讀 Opt-out。
- **裁判日期**：2024 年（德國漢堡地方法院）。

---

## 2. 案件事實與資料集建置流程 (LAION Pipeline)

- **被告身分**：LAION 為一德國非營利組織，其建立的開放資料集（如 LAION 5B）係 Stable Diffusion 圖像生成模型的訓練基石。
- **建置技術手法**：
  1. LAION 自既有網址清單中，下載公開於網路圖庫且帶有浮水印之預覽圖片至伺服器。
  2. 使用自動化軟體比對下載之圖像與文字敘述（Caption）是否相符，剔除不合者。
  3. 彙整一致者形成公開資料集，資料集僅包含原始圖片之網址連結與說明文字（未直接重新上傳圖片檔供下載）。
- **原告主張**：原告攝影師指控 LAION 在比對驗證過程中將其受保護之照片下載暫存於硬碟，侵害其著作重製權。

---

## 3. 法院核心裁判理由 (Judicial Reasoning)

### 3.1 適用科學研究之 TDM 豁免（德著第 60d 條 / CDSM 第 3 條）
- 法院認定，建立供 AI 模型訓練之資料集，屬於為獲取新知識之「科學研究」各階段必要工作步驟。
- 只要從事資料探勘之主體具備非營利性質，且未受營利企業之實質控制，即使該資料集未來被營利性科技公司（如 Stability AI）用於商業模型訓練，亦不影響 LAION 本身享有科研 TDM 豁免。

### 3.2 震驚業界之附帶意見：自然語言可構成「機器可讀」退出！
- 原告張貼照片之網站於服務條款（Terms of Service）中以自然語言寫道：「禁止將本網站圖片用於自動化資料採集與 AI 訓練」。
- 法院於附帶意見（Obiter Dictum）中指出：
  - CDSM 第 4 條所謂之「機器可讀（Machine-readable）」，在現代自然語言處理（NLP）與 AI 技術進展下，應解釋為**「機器可理解（Machine-understandable）」**。
  - 因此，以自然語言寫成的使用條款，已足使網路爬蟲理解其保留之意思，構成合法有效的退出權（Opt-out）行使！

---

## 4. 產業與合規啟示 (Enterprise Takeaways)
> [!IMPORTANT]
> **本案對跨國 AI 模型開發者的雙重啟示：**
1. **防範「資料洗錢（Data Laundering）」審查**：
   - 商業公司若透過贊助非營利機構抓取資料來規避歐盟 CDSM 第 4 條的退出限制，正受到歐盟主管機關的高度關注與技術防堵。
2. **自然語言 Opt-out 的法律效力攀升**：
   - 傳統觀念認為必須在網站根目錄設置 `robots.txt` 或特定元數據標籤才算有效退出；但本案表明，網站 TOS 中的文字聲明在歐洲法庭上有極高機率被直接認定為有效退出。

---

## 5. 簡報提煉模組 (Slide Ready Bullets)
- **歐洲首例**：德國漢堡法院判決非營利組織建置 AI 訓練資料集（LAION）符合科學研究 TDM 免責。
- **突破性解釋**：法院認為在 AI 時代，「機器可讀」等同「機器可理解」，自然語言服務條款亦屬合法 Opt-out！
- **商業警惕**：歐盟 AI Act 實施後，商業模型若取用標註退出的資料，將面臨最高全球營收 3% 罰鍰。
