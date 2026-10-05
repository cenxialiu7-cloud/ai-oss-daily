# AI 求職作戰台：職缺掃描 → 依履歷 1–5 分配對 → 客製 ATS 履歷與求職信 → 面試準備與投遞追蹤，非工程師也能用的圖形版

career-ops 已證明『AI 幫你篩職缺、改履歷、你自己按送出』有大量需求（7.3 萬★），但它只跑在終端機與 AI coding 工具裡；本案把它包成一般求職者能直接用的網頁／Mac App，並補上在地求職平台、長期記憶與面試行事曆追蹤。

**怎麼變現**：①求職季訂閱（主力）：免費層每月少量職缺評分與 1 份客製履歷；付費層按月計費，含無限評分、每職缺客製履歷＋求職信、面試題庫與模擬問答，鎖定轉職者與應屆畢業生，求職期通常 1–3 個月，用短期月費而非年約降低決策門檻。②B2B 授權：賣給補習班、職涯顧問、大學職涯中心與轉職訓練營，按學員席次計費，附後台看學員投遞與面試進度。③單次加購：資深顧問人工潤稿、英文履歷在地化等按件收費。④求職教學內容站：『ATS 履歷怎麼寫』『各產業面試題』等長尾頁，網頁端掛 Adsterra／Monetag 廣告並導流主產品；開源小工具頁放 Ko-fi 贊助。全案不涉及任何 VPN 類聯盟。

**運作方式**：四層架構，投遞一律由使用者本人按下送出。①核心引擎：github:career-ops-hq/career-ops（MIT，變現核心）提供職缺掃描、依履歷 1–5 分評分、ATS 友善履歷與求職信生成、面試準備與投遞追蹤；本案把它的 skill／CLI 流程包成後端工作佇列，前端做成表單與看板介面，並新增在地職缺來源的擷取器（優先用各平台公開職缺頁與官方合作管道）。②長期記憶層：github:thedotmack/claude-mem（Apache-2.0）記錄使用者每次投遞的版本、被拒原因、面試回饋與偏好，下次評分與改寫時自動帶入，讓履歷越用越準，形成留存。③文件理解層：hf:model:deepseek-ai/DeepSeek-V4.1-Flash（圖文轉文字）讀取使用者上傳的舊履歷 PDF／截圖、作品集與職缺截圖，轉成結構化欄位，省去手動輸入。④行事曆與信件層：github:oomol-lab/open-connector（Apache-2.0）以 OAuth 接上使用者的 Gmail／Google Calendar，自動把面試邀約歸檔到看板並建立行程提醒；github:modelcontextprotocol/python-sdk 再把『我的求職看板』包成 MCP，讓進階使用者在 Claude 等 AI 工具內直接查詢與更新。與現有企劃區隔：P037 的 claude-mem 用於開發記憶，P059 是商機郵件管家；目前沒有任何企劃覆蓋 C 端求職場景。

**難度**：medium · **投入估計**：估 3–4 週做出能跑版本：career-ops 流程包成後端服務＋網頁看板約 1.5 週；履歷／職缺文件解析與 claude-mem 記憶接入約 1 週；open-connector 信件與行事曆串接、計價頁約 1 週。難點：一是各求職平台條款多禁止自動化爬取，職缺來源須以公開頁、RSS、使用者手動貼上連結為主，不做大量爬取與自動投遞；二是 DeepSeek-V4.1-Flash 在目錄授權標為『需人工確認』（標 mit 但代碼未被系統辨識），上線前核對模型卡，必要時改用其他可商用多模態模型或雲端 API，不影響主流程；三是履歷含大量個資，須做加密儲存、可一鍵刪除，並依個資法揭露用途；四是 career-ops 原生以英文市場為主，繁中履歷格式與在地 ATS 慣例需另做模板與提示詞。

## 用到的開源零件

- [career-ops-hq/career-ops](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/career-ops-hq-career-ops/) — 自動化職業搜尋和申請流程的AI代理。
- [thedotmack/claude-mem](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/thedotmack-claude-mem/) — Claude Agent 的持久上下文跨會話系統，捕獲並壓縮會話內容。
- [deepseek-ai/DeepSeek-V4.1-Flash](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-deepseek-ai-deepseek-v4-1-flash/) — 將影像和文字轉換為文字的模型。
- [oomol-lab/open-connector](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/oomol-lab-open-connector/) — 開源認證門戶，連線SaaS供應商與AI代理。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
