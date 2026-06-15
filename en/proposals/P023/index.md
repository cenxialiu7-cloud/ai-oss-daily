# 設計系統抽取 → 一鍵改版／競品仿建 SaaS：丟一個網址，產出可改的設計系統與頁面

輸入任一網站，自動抽出它的設計系統（色/字/元件），再用 AI 生成你的版本或競品分析，給接案者/小團隊快速建站。

**Monetization**：①SaaS 訂閱（按專案/席次）②Gumroad 賣『競品設計拆解報告＋可改版模板』買斷做漏斗 ③接案者代建站服務 ④落地頁 Adsterra/Monetag＋Ko-fi。沿用 OSS Radar 報告/發佈模板出可交付物。

**How it works**：貼網址 → design-extract 抽出色票/字體/間距/元件清單 → open-design 依抽出系統生成『你的版本』或競品對照 → html-anything 重組成可編輯頁面 → 以 specification.website 為 rubric 打『規格/無障礙/SEO 分數』→ 輸出設計系統文件＋可改版頁面＋拆解報告（OSS Radar 模板）。

**Difficulty**：medium · **Effort**：3 週（抽取→生成→重組串接＋報告模板＋訂閱閘門）。

## Open-source parts

- [Manavarya09/design-extract](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/manavarya09-design-extract/) — Extract any website's complete design system with one command. DTCG tokens, semantic+primitive+composite, MCP…
- [nexu-io/open-design](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/nexu-io-open-design/) — 🎨 Local-first, open-source Claude Design alternative. 🖥️ Native desktop app. ⚡ 259+ Skills · ✨ 142+ Design Sy…
- [nexu-io/html-anything](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/nexu-io-html-anything/) — ✨ The agentic HTML editor — your local AI agent writes the HTML, you ship it. 🚀 75 Skills × 9 Surfaces (magaz…
- [jdevalk/specification.website](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/jdevalk-specification-website/) — Website specification — HTML, accessibility, security, SEO, agent-readiness. Platform-agnostic, sourced, MIT.
