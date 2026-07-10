# AI 答案引擎可見度雷達：持續追蹤品牌與對手在 AI 答案中的被引用聲量

不是體檢一次，而是每天盯著你和對手在 AI 搜尋答案（AI Overviews／聊天式搜尋）被提及與引用了多少，聲量掉了就示警。

**怎麼變現**：①SaaS 月費：依追蹤品牌數／關鍵字數／快照頻率分級（如 3 品牌 20 關鍵字週更 vs 日更）；②網頁端公開『產業 AI 可見度排行榜』吃自然流量、掛 Adsterra／Monetag 廣告並導流試用；③行銷代理商白標月報授權＋Ko-fi 贊助，另接 SEO／看盤工具與主機商聯盟分潤。廣告只放網頁端，絕不碰任何 VPN 類聯盟。

**運作方式**：crawlie／SEOCORE 先爬你與競品站台，建立頁面與主題清單 → potato 針對追蹤關鍵字，量測品牌在搜尋與 AI 答案中的被提及次數與被引用來源 → orangeo-ai-visibility-skill 打 AI 可見度分數並計算對手落差 → 用 modelcontextprotocol/python-sdk 把整套包成 MCP 工具＋排程每日快照，累積『聲量趨勢／share-of-voice』時序資料 → 儀表板呈現趨勢與競品對比，分數下滑自動 email／LINE 示警。與 P014（一次性可引用性稽核）互補而非重疊：P014 是修站體檢，本案是持續監測實際被引聲量與對手基準的 BI／追蹤層。

**難度**：medium · **投入估計**：估 2–3 週做出能跑的 MVP：爬站→量測→評分管線約一週可通，儀表板與排程快照約一週；難點在穩定地對多個 AI 答案引擎抓取並解析『被引用來源』（速率限制、反爬、引用歸屬正規化），以及跨引擎統一 share-of-voice 指標。

## 用到的開源零件

- [onism1767-creator/potato](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/onism1767-creator-potato/) — 測量品牌在網頁搜尋結果中的提及頻率和引用次數。
- [PixelOrange7/orangeo-ai-visibility-skill](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/pixelorange7-orangeo-ai-visibility-skill/) — 開源AI可見性檢查工具，用於評估網站SEO和競爭對手差距。
- [codepurse/SEOCORE](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/codepurse-seocore/) — SEOCORE 是一個企業級 SEO 網站爬蟲工具，適用於多執行緒執行和深度網站健康審計。
- [spronta/crawlie](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/spronta-crawlie/) — 快速、免費且開源的技術 SEO 和 GEO 網站爬蟲工具。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
