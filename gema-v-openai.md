---
title: "GEMA v. OpenAI"
alias: ["德國音樂著作權協會訴 OpenAI 案", "GEMA 歌詞記憶化判決案"]
filed_date: 2024-11-13
court: "Landgericht München I (德國慕尼黑第一地方法院)"
case_no: "42 O 14139/24"
judgment_date: 2025-11-11
status: "Judgment for Plaintiff (原告勝訴)"
modality: "Text & LLM (Lyrics)"
target_entity: "OpenAI Ireland Ltd. / OpenAI Inc."
plaintiff: "GEMA (Gesellschaft für musikalische Aufführungs- und mechanische Vervielfältigungsrechte, 德國音樂著作仲介團體)"
core_issues:
  - "Memorization & Regurgitation (模型記憶化與原樣吐出)"
  - "TDM Defense Failure (歐盟 CDSM 指令第 3/4 條 TDM 例外排除適用)"
  - "Unauthorized Direct Reproduction (未經授權直接重製)"
  - "Direct Model Provider Liability (模型提供商直接侵權責任)"
risk_level: "High"
slide_ready: true
---

# GEMA v. OpenAI (慕尼黑第一地方法院 2025 年判決)

## 1. 案件基本概況 (Executive Overview)
- **一句話定調**：歐洲首件正式裁定大型語言模型（LLM）記憶化輸出受保護歌詞構成「未經授權著作重製」並明確排除 TDM 免責適用的里程碑判決。
- **裁判結果**：2025 年 11 月 11 日，德國慕尼黑第一地方法院（Landgericht München I，案號 42 O 14139/24）判決原告 GEMA 勝訴。法院認定 OpenAI 旗下的 GPT-4 及 GPT-4o 能夠幾乎一字不差地吐出（Regurgitate）受著作權保護之德國知名歌詞，構成對著作權人重製權之侵害；同時駁回了 OpenAI 關於歐盟文本與數據探勘（TDM）的豁免抗辯。

---

## 2. 訴訟事實與技術舉證 (Factual Background & Technical Evidence)

### (1) 起訴事實
原告 GEMA 代表德國多位知名詞曲創作者（如兒童音樂大師 Rolf Zuckowski 等）對 OpenAI 提起侵權訴訟，指控：
1. OpenAI 未經授權，在其模型訓練中攝入海量德國受著作權保護之音樂歌詞。
2. 當一般使用者在 ChatGPT（GPT-4、GPT-4o）輸入特定歌詞提示詞（如提供歌曲名稱、首句歌詞或創作者姓名）時，模型能以極高精確度輸出整段或整首受保護之原創歌詞。

### (2) 被告 OpenAI 的主要抗辯
1. **未在模型內部儲存複製品**：OpenAI 主張神經網路權重僅包含機率分佈與抽象概念，不包含任何具體檔案或文本重製物。
2. **歐盟 TDM 例外豁免**：依據歐盟 CDSM 指令（Directive (EU) 2019/790）第 3 條及第 4 條（對應德國著作權法 UrhG § 44b），為進行文本與數據探勘所為之重製享有法定例外。
3. **安全防護已足夠**：輸出原樣內容係使用者利用對抗性誘導所致，並非系統預設功能。

---

## 3. 法院核心裁判理由 (Court Rationale)

### (1) 模型記憶化輸出構成「實質重製」（Reproduction）
慕尼黑地院認定：
- 無論技術架構宣稱模型是如何計算「下一個 Token 的機率分佈」，從客觀產出結果觀察，ChatGPT 輸出的文本與原告享有著作權之歌詞具有實質同一性（Substantial Identity）。
- 這種近乎 100% 逐字逐句的重現（Regurgitation），本質上就是著作權法上受專屬保護之重製行為。

### (2) 徹底破除 TDM 例外抗辯（No Safe Harbor under EU CDSM Art. 3/4）
法院採納了歐洲學界（包含 Tim W. Dornis 等法學家）之權威見解：
- **TDM 之立法意旨**：是為了容許機器進行非表達性資訊抽取（Semantic and factual pattern discovery），即「為了分析而非為了消費或替代」。
- **生成式 AI 的訓練本質**：並非為了探索客觀統計事實，而是為了吸納原作的表達形式（Expressive Quality），進而在下游重現或生成替代性作品。
- **結論**：歐盟 CDSM 指令第 4 條（UrhG § 44b）所規定之商業 TDM 例外，**不得涵蓋為生成對抗或生成式目的所進行的模型訓練與記憶化重現**。

### (3) 模型提供商應負直接侵權責任（Direct Liability）
法院駁回了 OpenAI 將責任轉嫁給終端使用者的主張，明確指出：
- 記憶化能力是由 OpenAI 於預訓練與微調過程中所建構；
- OpenAI 提供該商業服務並從中獲利，對其模型記憶化溢出負有客觀防範與直接侵權責任。

---

## 4. 產業與合規衝擊 (Industry & Compliance Impact)

1. **歐洲「TDM 免責金牌」全面破滅**：
   - 長期以來，許多在歐洲營運或採集資料的 AI 公司依賴 CDSM 第 4 條作為抗辯護城河。慕尼黑判決確立了：只要模型具備記憶化並吐出受保護內容之能力，TDM 免責條款即告失效。
2. **記憶化成為客觀侵權標籤**：
   - 法院不理會模型「學會而非儲存」的修辭，直接以輸出端是否存在表達性實質相似作為判斷核心。
3. **推論防護（Inference Guardrails）的法律脆弱性**：
   - 僅在事後推論時使用 Prompt 防護攔截關鍵詞無法作為免責盾牌；一旦原告能繞過並觸發記憶化，即足以證立前端訓練與模型儲存階段之侵權。

---

## 5. 簡報提煉模組 (Slide Ready Bullets)

- **歐洲第一刀**：德國慕尼黑第一地方法院判決 GEMA 控告 OpenAI 勝訴，GPT-4/4o 記憶歌詞構成侵權。
- **TDM 假面被戳破**：法院認定生成式 AI 訓練並非歐盟 CDSM 法定的「數據探勘（TDM）」，無法享有免責例外。
- **客觀結果主義**：法官不採信「神經網路不存檔案」的技術辯解，模型吐出歌詞即屬違法重製。
- **廠商直接責任**：模型供應商對其模型記憶化輸出負直接侵權責任，不能推託給使用者的 Prompt 誘導。
