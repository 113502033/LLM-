---
title: "RIAA v. Suno & Udio"
alias: ["美國唱片業協會訴 Suno 及 Udio 案", "音樂生成 AI 著作權訴訟案"]
filed_date: 2024-06-24
court: "U.S. District Court for the District of Massachusetts (Suno) / S.D.N.Y. (Udio)"
case_no: "1:24-cv-11611 (D. Mass. - Suno) / 1:24-cv-04777 (S.D.N.Y. - Udio)"
status: "Active / Pre-trial"
modality: "Audio & Music AI"
target_entity: "Suno, Inc. / Uncharted Labs, Inc. (Udio)"
plaintiff: "Recording Industry Association of America (RIAA) 代表 Sony Music, Universal Music Group (UMG), Warner Music Group 等唱片巨頭"
core_issues:
  - "Fair Use (合理使用四要素抗辯)"
  - "Web Scraping of Master Sound Recordings (全網未經授權母帶錄音爬取)"
  - "Audio Memorization & Timbre Replication (音色、旋律與編曲特徵之記憶化)"
  - "Market Substitution for Commercial Sound Recordings (商業音樂市場之直接替代)"
  - "Neural Audio Codecs as Codebooks (神經編解碼器代碼簿版權風險)"
risk_level: "High"
slide_ready: true
---

# RIAA v. Suno & Udio (音樂生成 AI 侵權訴訟案)

## 1. 案件基本概況 (Executive Overview)
- **一句話定調**：全球音樂產業對抗生成式 AI 公司的第一場大規模正面戰役。訴訟直接拷問：未經許可使用數百萬首受版權保護的錄音母帶訓練商業化音樂生成模型，是否能構成美國法上的「合理使用（Fair Use）」？
- **當前訴訟進展**：2024 年 6 月 24 日由美國唱片業協會（RIAA）協同 Sony Music、UMG、Warner 等三大唱片公司分別向麻州聯邦地院（控告 Suno）與紐約南區聯邦地院（控告 Udio）提起訴訟，求償每首被侵權錄音物法定最高 150,000 美元之損害賠償。2024 年 8 月，Suno 首度在答辯狀中公開承認其模型確實使用了版權音樂進行訓練，但主張此屬典型「合理使用」。目前案件仍在實質審理程序中。

---

## 2. 訴訟事實與爭議焦點 (Factual Background & Core Contentions)

### (1) 原告指控事實
1. **未經授權爬取海量商業母帶**：原告指控 Suno 與 Udio 建立的百億級音樂生成系統，並非單純從免費開源音訊或公有領域作品訓練，而是全面性爬取串流平台與網路上的高品質商業錄音檔案（包含錄音著作 Sound Recordings 與詞曲音樂著作 Musical Compositions）。
2. **記憶化特徵外溢舉證**：
   - 原告律師在訴狀中附上了大量生成音訊比對，證明輸入特定風格、歌名或藝人提示詞時，模型生成出了近乎難以區分的標誌性人聲音色（如 Mariah Carey、Michael Jackson、Bruce Springsteen）、經典吉他 Riff（如 Chuck Berry 之《Johnny B. Goode》）、甚至原曲的獨特人聲標記與合聲編曲。
3. **商業毀滅性競爭**：Suno 與 Udio 提供即時文字生音樂（Text-to-Music）服務，使用者數秒內即可生成完整廣播級歌曲，其市場目的就是直接替代商業背景音樂、影視配樂與音樂串流收聽，對錄音產業造成不可逆的市場稀釋。

### (2) 被告 Suno 與 Udio 的核心答辯
1. **學習而非複製（Learning vs. Copying）**：Suno 主張其 AI 模型的運作方式與人類音樂學院學生無異——博覽各類風格與經典名曲以學習「音樂的文法、調性、節奏與配器規則」，訓練完畢後模型權重僅保存統計規律，而非儲存原音訊音檔。
2. **中間重製屬於合理使用（Intermediate Copying / Transformative Use）**：援引 *Sega v. Accolade*、*Kelly v. Arriba Soft* 與 *Authors Guild v. Google*（Google Books 案），主張後端訓練抓取屬於中間性重製（Intermediate Copying），最終產出的歌曲均為全新且原創之音樂作品，具備極高轉化性。
3. **反對唱片巨頭壟斷競爭**：被告指責大型唱片公司試圖藉由著作權封殺新興技術工具，扼殺一般大眾的音樂創作平權。

---

## 3. 跨領域深度技術解析：音樂 AI 為何比文本 AI 更致命？ (Stober & Dornis 觀點)

根據計算機科學家 Sebastian Stober 與法學教授 Tim W. Dornis 在 2026 年論文中的技術與法律論證，音樂生成 AI 面臨遠高於文本語言模型的法律風險：

### (1) 神經音訊編解碼器（Neural Audio Codecs）的「代碼簿」本質
- 傳統文本 LLM 處理的是離散 Token（單詞/字元），而音樂音訊需要透過神經編解碼器（如 Meta EnCodec、SoundStream、Descript Audio Codec）將連續音訊壓縮為量化的離散潛在代碼（Residual Vector Quantization, RVQ）。
- 這些解碼器的**代碼簿（Codebook）與潛在空間並非單純的數值壓縮演算法**，而是利用生成對抗網路（GAN）或擴散架構進行聲學重建。若模型解碼輸出的聲音特徵包含了訓練時特定錄音的細膩音色與聲學細節，這意味著該聲音特徵是**物理性刻入於權重代碼簿中**。
- **法律定性**：散布包含此類代碼簿權重的模型，在法律上即構成散布受保護錄音物的實質衍生重製物！

### (2) 音樂表達的高度凝練性
- 與數萬字的長篇著作不同，一段 3 秒鐘的標誌性吉他 Solos 或特定的人聲音色，在著作權法上就具備高度的原創表達（Originality）。因此，只要模型發生微小的記憶化效應（Memorization Effect），即極易跨越「實質相似性（Substantial Similarity）」門檻。

---

## 4. 產業與合規啟示 (Enterprise & Developer Takeaways)

1. **直接承認訓練資料來源的法律豪賭**：
   - Suno 採取了高風險訴訟策略，正面承認抓取版權母帶並全賭在「合理使用第一要素（轉化性）」上。如果法院如 *Bartz v. Anthropic* 般認定「未經授權大量下載版權物無法被轉化性治癒」，Suno 將面臨毀滅性的法定賠償。
2. **多模態訓練資料授權成為必備門檻**：
   - 音訊與音樂生成開發商不能再心存僥倖援引「網路公開即可抓取」。商業模型必須轉向與唱片公司、曲庫平台建立正式授權協議（如 YouTube 與三大唱片簽署的 AI 音樂試驗協議）。
3. **聲學特徵與音色防護的急迫性**：
   - 音樂模型必須在推論層建立即時音訊指紋比對機制（如 AcoustID / Chromaprint 攔截），防止使用者誘導出知名歌手音色或標誌性旋律。

---

## 5. 簡報提煉模組 (Slide Ready Bullets)

- **唱片巨頭全面宣戰**：RIAA 聯合三大唱片公司起訴 Suno 與 Udio，每首錄音索賠最高 15 萬美元。
- **被告承認抓取母帶**：Suno 於答辯中公開坦承訓練集包含受保護錄音，將全案押注於「合理使用（Fair Use）」。
- **音樂 AI 的物理重現風險**：神經編解碼器（Neural Audio Codec）的代碼簿實質儲存聲學特徵，比文字模型更容易構成實質相似。
- **授權為唯一正道**：未經許可抓取串流商業音訊訓練，極可能引發音樂產業滅頂級的版權索賠風暴。
