# AI 答案引擎可見度雷達：持續追蹤品牌與對手在 AI 答案中的被引用聲量

不是體檢一次，而是每天盯著你和對手在 AI 搜尋答案（AI Overviews／聊天式搜尋）被提及與引用了多少，聲量掉了就示警。

**Monetization**：①SaaS 月費：依追蹤品牌數／關鍵字數／快照頻率分級（如 3 品牌 20 關鍵字週更 vs 日更）；②網頁端公開『產業 AI 可見度排行榜』吃自然流量、掛 Adsterra／Monetag 廣告並導流試用；③行銷代理商白標月報授權＋Ko-fi 贊助，另接 SEO／看盤工具與主機商聯盟分潤。廣告只放網頁端，絕不碰任何 VPN 類聯盟。

**How it works**：crawlie／SEOCORE 先爬你與競品站台，建立頁面與主題清單 → potato 針對追蹤關鍵字，量測品牌在搜尋與 AI 答案中的被提及次數與被引用來源 → orangeo-ai-visibility-skill 打 AI 可見度分數並計算對手落差 → 用 modelcontextprotocol/python-sdk 把整套包成 MCP 工具＋排程每日快照，累積『聲量趨勢／share-of-voice』時序資料 → 儀表板呈現趨勢與競品對比，分數下滑自動 email／LINE 示警。與 P014（一次性可引用性稽核）互補而非重疊：P014 是修站體檢，本案是持續監測實際被引聲量與對手基準的 BI／追蹤層。

**Difficulty**：medium · **Effort**：估 2–3 週做出能跑的 MVP：爬站→量測→評分管線約一週可通，儀表板與排程快照約一週；難點在穩定地對多個 AI 答案引擎抓取並解析『被引用來源』（速率限制、反爬、引用歸屬正規化），以及跨引擎統一 share-of-voice 指標。

## Open-source parts

- [onism1767-creator/potato](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/onism1767-creator-potato/) — Free Easy AI visibility check - measure how often a brand is mentioned & cited in Claude's web-search answers…
- [PixelOrange7/orangeo-ai-visibility-skill](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/pixelorange7-orangeo-ai-visibility-skill/) — Open-source GEO / AEO skill for AI visibility readiness: check robots.txt, llms.txt, schema, citation signals…
- [codepurse/SEOCORE](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/codepurse-seocore/) — Enterprise-grade, multi-threaded SEO Crawler, Rule Engine, and Link Graph Analyzer. Built in TypeScript for s…
- [spronta/crawlie](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/spronta-crawlie/) — Fast, free, open-source technical SEO + GEO crawler: built for humans and agents.
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/modelcontextprotocol-python-sdk/) — The official Python SDK for Model Context Protocol servers and clients
