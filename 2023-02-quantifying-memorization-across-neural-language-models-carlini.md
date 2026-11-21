# Quantifying Memorization Across Neural Language Models (量化神經語言模型中的記憶化現象)

- **作者**：Nicholas Carlini, Daphne Ippolito, Matthew Jagielski, Katherine Lee, Florian Tramèr, Chiyuan Zhang（Google Research, Google DeepMind, Stanford University, ETH Zürich）
- **文獻來源**：ICLR 2023 (The Eleventh International Conference on Learning Representations) / arXiv:2202.07646v4
- **原文收錄**：`raw/papers/2023-02-quantifying-memorization-across-neural-language-models-carlini.md`

---

## 核心綱要與技術實證突破

本論文係 AI 安全、隱私計算與生成式 AI 著作權訴訟領域最具權威性的開創性實證研究。作者團隊對數十種開源語言模型（包含 GPT-2、GPT-Neo、GPT-J 系列）進行了數十億 Token 的記憶化抽取實驗，首次精確量化了神經網路對訓練資料的記憶規律。

### 1. 核心定義：k-Eidetic 記憶化（k-Eidetic Memorization）
- 一段長度為 $N$ 的文字序列 $s$，若在訓練集中出現次數最多為 $k$ 次，且模型在給定前綴 $p$ 時能夠以貪婪解碼（Greedy Decoding）近乎 100% 逐字輸出後續文字，則稱該模型對 $s$ 產生了 **k-Eidetic Memorization**。
- **實證震撼**：即使 $k=1$（即特定文章在包含數千億 Token 的訓練集中僅出現過一次），超大參數模型依然能夠將其精確刻入權重並被對抗性抽取！

### 2. 模型記憶化三大對數線性標度律（The 3 Scaling Laws of Memorization）

Carlini 等人發現並以數學公式確立了決定模型記憶化強度的三大關鍵變數：

1. **模型參數規模（Model Capacity）**：
   - 記憶化比例隨模型參數規模呈**對數線性（Log-linear）暴增**。在相同訓練條件下，70B 參數模型的記憶化抽取率是 7B 模型的數倍至數十倍。
2. **訓練資料重複頻率（Data Duplication Factor）**：
   - 重複次數是誘發記憶化的最致命催化劑。若特定版權文本或代碼在網路爬蟲語料中重複出現超過 10~50 次，模型對其精確記憶並原樣吐出的機率呈超線性上升。
3. **提示詞前綴長度（Prompt Context Prefix Length）**：
   - 提示前綴長度與記憶化成功率呈對數正相關。當原告或使用者提供超過 50 個 Token 的前綴時，模型的條件機率分佈會收窄至單一路徑（通道視野效應），極難發散生成原創內容。

### 3. 對著作權司法實務的決定性影響
- **擊破「大腦抽象學習」抗辯**：本論文直接提供了法庭呈堂證據，證明神經網路權重並非單純學習統計概念，而是物理性儲存了特定樣本。
- **去重（Deduplication）工程的法律效益**：論文證實，若在預訓練前實施嚴格的資料去重（如 MinHash LSH），可將模型記憶化洩漏的機率降低 80% 以上，成為企業防禦版權侵權的最有效工程手段。
