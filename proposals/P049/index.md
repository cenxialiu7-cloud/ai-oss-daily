# 本機技術 SEO 體檢台（Mac App）：一鍵爬站 → 70+ 項技術 SEO 診斷 + GSC／GA4 對照，附 GEO 加分層

丟一個網域，本機完整爬站、跑 70+ 項技術 SEO 檢查並串接 Search Console／GA4，產出可白標交付的體檢報告；再疊一層 GEO 診斷看內容能不能被 AI 答案引用。

**怎麼變現**：①Mac App 買斷：本機工作台含 70+ 檢查引擎與自訂爬蟲，資料在本機、適合接案者與中小企業；②Ko-fi 解鎖白標報告模板（接案者可換上客戶 logo 直接交付）；③主機商／CDN／效能工具聯盟：報告內的修復建議自然導流。公開的免費線上迷你檢測頁掛 Adsterra／Monetag 廣告衝自然流量。絕不碰任何 VPN 類聯盟。

**運作方式**：以 iannuttall/seo 當核心引擎，提供自訂爬蟲 + 70+ 項技術 SEO 檢查（索引、爬取錯誤、Core Web Vitals、結構化資料等）並串接 Search Console／GA4 拉實際流量與查詢資料 → on-page-ai/geo-seo-superapp 提供 macOS 工作空間 UI 當外殼，把爬取與檢查結果整併成一份可讀報告 → aigclink/geolook 加一層 GEO 診斷（內容能否被 AI 答案引用）當加分項 → 用 modelcontextprotocol/python-sdk 讓 Claude 一句話跑『幫這個網域做完整技術體檢並出報告』，輸出繁中可白標 HTML／PDF。與 P002（GEO 內容生產）、P014（每月 GEO 稽核 SaaS）、P040（AI 答案可見度追蹤）定位不同：本案核心是傳統 Google 技術 SEO 的一次性深度體檢工具（本機 Mac App），GEO 只是加分層，非以 GEO 為賣點。

**難度**：medium · **投入估計**：估 3–4 週做出能跑版本：iannuttall/seo 爬蟲與檢查引擎接入約 1 週，Search Console／GA4 OAuth 授權與資料串接約 1 週，superapp UI 整併報告與 geolook GEO 層約 1 週，白標報告輸出約 0.5 週。難點在 GSC／GA4 的 OAuth 授權流程、大站爬取的效能與速率限制，以及把三個工具的輸出整併成一份一致的可交付報告。

## 用到的開源零件

- [iannuttall/seo](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/iannuttall-seo/) — 提供70多種SEO審核工具，透過本地CLI和MCP伺服器使用自定義爬蟲、Search Console和GA4資料。
- [on-page-ai/geo-seo-superapp](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/on-page-ai-geo-seo-superapp/) — 免費的 macOS 工作空間，專為 SEO 和 GEO 機構設計。
- [aigclink/geolook](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/aigclink-geolook/) — 開源 GEO 實施工具，涵蓋狀態分析、診斷等。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
