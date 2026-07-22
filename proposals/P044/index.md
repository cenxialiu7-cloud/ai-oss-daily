# 報表機器人：接上資料源 → 每月自動產出帶「可信圖表」的客戶月報與營運報表

把行銷代理商與顧問每月手工做客戶月報的苦差事自動化：取數、產圖、寫繁中解讀一次完成；圖表由規格語言渲染而非讓 LLM 直接畫，數字不會被編出來。

**怎麼變現**：①SaaS 月費：按「客戶數 × 每月報表數」分級，主客群是行銷代理商、記帳與顧問業；②Mac App 買斷：本機版直接連客戶的試算表或資料庫，資料不出機，適合合約有保密條款的顧問；③範本市集：電商月報、廣告投放月報、SaaS 營運月報等現成版型單次付費。公開的報表範本展示站掛 Adsterra／Monetag 網頁廣告並放 Ko-fi 贊助。廣告只放網頁端。

**運作方式**：livecontext-ai/livecontext-ce 當自動化骨架，用自然語言描述「每月 1 號拉上月資料、產出這幾張圖、寄給客戶」並生成可重跑的工作流程 → 用 modelcontextprotocol/python-sdk 把資料源（試算表、資料庫、各平台匯出檔）包成 MCP 工具，讓 agent 以查詢取數而不是憑印象生成數字 → microsoft/flint-chart 是本案關鍵：agent 只負責產出「圖表規格」，由 flint-chart 這個視覺化語言渲染成圖，避開 LLM 直接畫圖時常見的軸標錯置與數值對不上 → hf:model:zai-org/GLM-5.2 只負責寫解讀文字（變化幅度、可能原因、下月建議），並限制只能引用查詢回來的數值，產出後再對數驗證一次 → nexu-io/html-anything 把圖表與敘述排成可寄送的 HTML 報表或 PDF，套用客戶品牌色。與 P020（廣告投放管家）分工不同：P020 是進帳戶做投放優化，本案完全不碰帳戶設定，專做跨資料源的報表產出與交付。

**難度**：medium · **投入估計**：估 3–4 週做出能跑的 MVP：資料源 MCP（試算表＋一個平台匯出檔）約 1 週，flint-chart 圖表規格產生與版型約 1 週，解讀文字的「只能引用查詢值」約束與事後對數驗算約 0.5–1 週，HTML／PDF 交付與排程寄送約 1 週。難點在資料清洗（客戶給的表格欄位每月都會變）與跨月欄位對齊，以及讓敘述文字與圖表數字保持一致。

## 用到的開源零件

- [microsoft/flint-chart](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/microsoft-flint-chart/) — 讓AI代理可靠地從簡單規格建立圖表的視覺化語言。
- [livecontext-ai/livecontext-ce](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/livecontext-ai-livecontext-ce/) — 自建AI自動化平臺，可描述任務並生成工作流程。
- [nexu-io/html-anything](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/nexu-io-html-anything/) — 本地 AI 最佳化 HTML 編輯器，支援多種設計表面。
- [zai-org/GLM-5.2](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-zai-org-glm-5-2/) — GLM-5.2 是一個支援多語言的文本生成模型，適用於對話和文章創作。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
