# 程式碼知識圖譜即服務：丟一個 repo → 可互動探索的架構地圖，加速 onboarding/code review

把任何程式庫自動轉成可點擊探索、可問答的知識圖譜，新人三天上手變三小時，同時省 98% 檢索 token。

**Monetization**：①SaaS 訂閱（按 repo 數/團隊席次）②macOS 桌面版買斷（離線、私有碼不外流，走 MoR）③對工程團隊/接案者賣『一次性 codebase 體檢報告』做漏斗 ④落地頁 Adsterra/Monetag＋Ko-fi。不碰 VPN。

**How it works**：指定 repo → Understand-Anything 建出函式/模組/依賴的可互動知識圖譜 → semble 提供省 token 的精準檢索讓問答便宜 → open-codex 自動走查產出『新人導覽路線＋風險熱點』→ 前端專案再用 design-extract 抽出設計系統。輸出互動式網頁＋PDF 體檢報告（沿用 OSS Radar 既有 Jinja2 模板）；私有版全本機跑、碼不外流。

**Difficulty**：medium · **Effort**：3–4 週（圖譜引擎串接＋報告模板＋訂閱/席次閘門；先 CLI/web MVP，再包桌面版）。

## Open-source parts

- [Egonex-AI/Understand-Anything](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/egonex-ai-understand-anything/) — Graphs that teach > graphs that impress. Turn any code into an interactive knowledge graph you can explore, s…
- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/minishlab-semble/) — Fast and Accurate Code Search for Agents. Uses ~98% fewer tokens than grep+read
- [iFurySt/open-codex-computer-use](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/ifuryst-open-codex-computer-use/) — 👾 Open Computer Use – Open-Source Alternative to Codex Computer Use
- [Manavarya09/design-extract](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/manavarya09-design-extract/) — Extract any website's complete design system with one command. DTCG tokens, semantic+primitive+composite, MCP…
