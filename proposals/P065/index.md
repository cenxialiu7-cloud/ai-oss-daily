# 本機 AI 語音輸入法（Mac App）：任何輸入框按快捷鍵說話 → 即時轉文字＋自動潤稿成可直接送出的文句，聲音不出這台電腦

雲端語音輸入工具多採月費且音訊上傳雲端，律師、醫療、工程團隊不能用；本案用 Apple Silicon 專用的低位元 STT 模型做全域語音輸入，再由本機 LLM 去贅字、補標點、改成郵件／Slack／程式提示詞語氣，買斷制、離線可用。

**怎麼變現**：①Mac App 買斷（主力）：一次付費永久使用，另提供大版本升級折扣；以『不用月費＋不上傳音訊』對比雲端競品。②Pro 加購：自訂詞彙表（醫療、法律、程式術語）、多種潤稿語氣模板、長時間聽寫與會議逐字稿模式，一次性解鎖。③團隊授權：給律所、診所、軟體團隊的多台授權包，附集中派送詞彙表與設定檔。④官網與教學頁：『語音寫程式提示詞』『Mac 語音輸入效率技巧』等長尾內容，網頁端掛 Adsterra／Monetag 廣告並導流下載；開源詞彙表放 Ko-fi 贊助。全案不涉及任何 VPN 類聯盟。

**運作方式**：原生 Swift 選單列 App＋本機推論，三段管線全程離線。①收音與辨識：按住全域快捷鍵開始收音，hf:model:FermionResearch/Phonon-2（CC-BY-4.0，可商用需署名，變現核心）以 MLX 在 Apple Silicon 上跑低位元量化 STT，處理短句即時聽寫；長時間聽寫與會議模式則切換到 hf:model:Edge0/Audio8-ASR-Infinite 的串流辨識（輔助元件，授權待確認）。②潤稿：辨識結果送進本機 LLM，hf:model:prism-ml/Ternary-Bonsai-2-27B-gguf（llama.cpp／Metal，2 位元三值量化，記憶體需求低）負責去口頭禪、補標點、套用使用者選的語氣模板（郵件、Slack、程式提示詞），並套用自訂詞彙表修正專有名詞；記憶體不足的機型改用較小模型或只做規則式清理。③輸出：透過 macOS 輔助使用 API 把結果貼回游標所在輸入框；同時以 github:modelcontextprotocol/python-sdk 開一個本機 MCP，讓 Claude Code 等 AI 工具可直接取用『最近一段語音指令』，形成『用說的下指令給 AI』的工作流。與現有企劃區隔：P061 是直播／會議字幕顯示，P011 是 TTS 配音，P012 是離線 LLM 工作台；全域語音輸入法這個每天高頻使用的入口尚無企劃覆蓋。

**難度**：medium · **投入估計**：估 3–4 週做出能跑版本：Swift 選單列 App、全域快捷鍵與輔助使用貼字約 1 週；Phonon-2 MLX 推論與串流切段約 1 週；本機 LLM 潤稿、語氣模板與詞彙表約 1 週；授權、上架與官網約 0.5–1 週。難點：一是 Phonon-2 基於 Parakeet-TDT 架構，可能以英文等歐語為主，中文辨識品質須實測，若不足則中文改走 Audio8-ASR-Infinite 或其他可商用中文 ASR，英文市場可先上線；二是 Audio8-ASR-Infinite 與 Ternary-Bonsai-2-27B 在目錄授權標為『需人工確認』（標 apache-2.0 但代碼未被系統辨識），只作可替換的輔助元件，上線前核對模型卡；三是 27B 即使三值量化仍需較大記憶體，須依機型自動降級；四是 Phonon-2 為 CC-BY-4.0，App 內關於頁與官網需標註來源。

## 用到的開源零件

- [FermionResearch/Phonon-2](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-fermionresearch-phonon-2/) — 一款適用於蘋果Silicon的低位元語音轉文字模型。
- [Edge0/Audio8-ASR-Infinite](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-edge0-audio8-asr-infinite/) — 自動語音辨識模型，支援即時語音轉文字。
- [prism-ml/Ternary-Bonsai-2-27B-gguf](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-prism-ml-ternary-bonsai-2-27b-gguf/) — 基於llama.cpp的TERNARY模型，用於文本生成，支援2位元運算。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
