# 程式碼知識圖譜即服務：丟一個 repo → 可互動探索的架構地圖，加速 onboarding/code review

把任何程式庫自動轉成可點擊探索、可問答的知識圖譜，新人三天上手變三小時，同時省 98% 檢索 token。

**怎麼變現**：①SaaS 訂閱（按 repo 數/團隊席次）②macOS 桌面版買斷（離線、私有碼不外流，走 MoR）③對工程團隊/接案者賣『一次性 codebase 體檢報告』做漏斗 ④落地頁 Adsterra/Monetag＋Ko-fi。不碰 VPN。

**運作方式**：指定 repo → Understand-Anything 建出函式/模組/依賴的可互動知識圖譜 → semble 提供省 token 的精準檢索讓問答便宜 → open-codex 自動走查產出『新人導覽路線＋風險熱點』→ 前端專案再用 design-extract 抽出設計系統。輸出互動式網頁＋PDF 體檢報告（沿用 OSS Radar 既有 Jinja2 模板）；私有版全本機跑、碼不外流。

**難度**：medium · **投入估計**：3–4 週（圖譜引擎串接＋報告模板＋訂閱/席次閘門；先 CLI/web MVP，再包桌面版）。

## 用到的開源零件

- [Egonex-AI/Understand-Anything](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/egonex-ai-understand-anything/) — 將程式碼轉換為可互動探索和查詢的知識圖形工具。
- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/minishlab-semble/) — 快速且精確的程式碼搜尋工具，比 grep+read 少用約 98% 的 token。
- [iFurySt/open-codex-computer-use](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/ifuryst-open-codex-computer-use/) — Codex Computer Use的開源替代方案，提高可訪問性。
- [Manavarya09/design-extract](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/manavarya09-design-extract/) — 從網站提取完整設計系統的Chrome擴充功能，支援多平臺發射器。
