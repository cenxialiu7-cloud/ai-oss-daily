# 設計系統抽取 → 一鍵改版／競品仿建 SaaS：丟一個網址，產出可改的設計系統與頁面

輸入任一網站，自動抽出它的設計系統（色/字/元件），再用 AI 生成你的版本或競品分析，給接案者/小團隊快速建站。

**怎麼變現**：①SaaS 訂閱（按專案/席次）②Gumroad 賣『競品設計拆解報告＋可改版模板』買斷做漏斗 ③接案者代建站服務 ④落地頁 Adsterra/Monetag＋Ko-fi。沿用 OSS Radar 報告/發佈模板出可交付物。

**運作方式**：貼網址 → design-extract 抽出色票/字體/間距/元件清單 → open-design 依抽出系統生成『你的版本』或競品對照 → html-anything 重組成可編輯頁面 → 以 specification.website 為 rubric 打『規格/無障礙/SEO 分數』→ 輸出設計系統文件＋可改版頁面＋拆解報告（OSS Radar 模板）。

**難度**：medium · **投入估計**：3 週（抽取→生成→重組串接＋報告模板＋訂閱閘門）。

## 用到的開源零件

- [Manavarya09/design-extract](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/manavarya09-design-extract/) — 從網站提取完整設計系統的Chrome擴充功能，支援多平臺發射器。
- [nexu-io/open-design](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/nexu-io-open-design/) — 本機優先的開源 Claude Design 替代品：原生桌面 App、259+ skills（+874★）。
- [nexu-io/html-anything](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/nexu-io-html-anything/) — 本地 AI 最佳化 HTML 編輯器，支援多種設計表面。
- [jdevalk/specification.website](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/jdevalk-specification-website/) — 網站規格標準：HTML、無障礙、安全、SEO、agent 可讀性（Yoast 創辦人作品）。
