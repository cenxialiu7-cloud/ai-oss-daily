# 本機技術 SEO 體檢台（Mac App）：一鍵爬站 → 70+ 項技術 SEO 診斷 + GSC／GA4 對照，附 GEO 加分層

丟一個網域，本機完整爬站、跑 70+ 項技術 SEO 檢查並串接 Search Console／GA4，產出可白標交付的體檢報告；再疊一層 GEO 診斷看內容能不能被 AI 答案引用。

**Monetization**：①Mac App 買斷：本機工作台含 70+ 檢查引擎與自訂爬蟲，資料在本機、適合接案者與中小企業；②Ko-fi 解鎖白標報告模板（接案者可換上客戶 logo 直接交付）；③主機商／CDN／效能工具聯盟：報告內的修復建議自然導流。公開的免費線上迷你檢測頁掛 Adsterra／Monetag 廣告衝自然流量。絕不碰任何 VPN 類聯盟。

**How it works**：以 iannuttall/seo 當核心引擎，提供自訂爬蟲 + 70+ 項技術 SEO 檢查（索引、爬取錯誤、Core Web Vitals、結構化資料等）並串接 Search Console／GA4 拉實際流量與查詢資料 → on-page-ai/geo-seo-superapp 提供 macOS 工作空間 UI 當外殼，把爬取與檢查結果整併成一份可讀報告 → aigclink/geolook 加一層 GEO 診斷（內容能否被 AI 答案引用）當加分項 → 用 modelcontextprotocol/python-sdk 讓 Claude 一句話跑『幫這個網域做完整技術體檢並出報告』，輸出繁中可白標 HTML／PDF。與 P002（GEO 內容生產）、P014（每月 GEO 稽核 SaaS）、P040（AI 答案可見度追蹤）定位不同：本案核心是傳統 Google 技術 SEO 的一次性深度體檢工具（本機 Mac App），GEO 只是加分層，非以 GEO 為賣點。

**Difficulty**：medium · **Effort**：估 3–4 週做出能跑版本：iannuttall/seo 爬蟲與檢查引擎接入約 1 週，Search Console／GA4 OAuth 授權與資料串接約 1 週，superapp UI 整併報告與 geolook GEO 層約 1 週，白標報告輸出約 0.5 週。難點在 GSC／GA4 的 OAuth 授權流程、大站爬取的效能與速率限制，以及把三個工具的輸出整併成一份一致的可交付報告。

## Open-source parts

- [iannuttall/seo](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/iannuttall-seo/) — The only SEO skill your agent needs. 70+ SEO audit tools through a local CLI and MCP server, using your own c…
- [on-page-ai/geo-seo-superapp](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/on-page-ai-geo-seo-superapp/) — Free macOS workspace for SEO and GEO agencies
- [aigclink/geolook](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/aigclink-geolook/) — Open-source end-to-end GEO implementation: status analysis, diagnosis, strategy, tickets, execution, verifica…
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/modelcontextprotocol-python-sdk/) — The official Python SDK for Model Context Protocol servers and clients
