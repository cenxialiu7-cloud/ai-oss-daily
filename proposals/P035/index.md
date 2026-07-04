# AI 企業盡職調查工作台：輸入公司／網域 → 自動彙整公開情報 → 產出風險與背景盡調報告

給徵才、投資、合規與品牌保護團隊：輸入一家公司或網域，AI 用 OSINT 自動跨源蒐集公開情報，彙整成一份含風險旗標與佐證連結的繁中盡職調查報告。

**怎麼變現**：①網頁端『免費快篩版』盡調摘要（單一公司基本公開情報＋風險提示）掛 Adsterra／Monetag 廣告引流；②完整報告付費解鎖（多來源交叉比對、風險旗標、佐證連結彙整）用 Ko-fi 一次性解鎖，或 SaaS 月費（批量查核、每週重掃、PDF／CSV 匯出，賣給 HR／投資／合規團隊）；③自架部署教學帶主機商聯盟分潤，桌面整理版另做 Mac App 買斷。全程僅用公開資料並附合規與免責聲明，絕不碰任何 VPN 類聯盟。

**運作方式**：OpenOSINT 當核心情報蒐集代理，用其 16 種工具跨網域、社群、公開登記與新聞來源，針對輸入的公司／網域抓取公開足跡（註冊資訊、關聯站點、外洩提及、品牌冒用等）→ baidu/Unlimited-OCR 把截圖、掃描登記文件或 PDF 轉成可比對文字 → semble 對彙整到的大量情報做高速檢索與去重，交叉比對出重複、矛盾與風險線索（比 grep+read 省約 98% token）→ GLM-5.2 將多語來源歸納成繁中盡調報告，標註風險旗標、信心度與佐證連結 → 以 modelcontextprotocol/python-sdk 包成 MCP／CLI，網頁端輸出可下載報告。僅蒐集公開資料、聚焦企業／網域層級的合規與商業盡職調查，非個人監控；與 P017 資安情報（CVE／紅隊、對象是自家程式碼漏洞）定位不同。

**難度**：medium · **投入估計**：估 2–4 週做出能跑的 MVP：接 OpenOSINT 與報告產生各約一週；難點在多來源情報去重與可信度評分、公開資料的合規與免責邊界、避免誤報造成名譽風險，以及查核結果的佐證連結可追溯性。

## 用到的開源零件

- [OpenOSINT/OpenOSINT](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/openosint-openosint/) — 結合16種工具的AI驅動情報收集代理程式，支援Claude、GPT-4等模型。
- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/minishlab-semble/) — 快速且精確的程式碼搜尋工具，比 grep+read 少用約 98% 的 token。
- [baidu/Unlimited-OCR](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-baidu-unlimited-ocr/) — 百度的無限 OCR 技術，將影像轉換為文字。
- [zai-org/GLM-5.2](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-zai-org-glm-5-2/) — GLM-5.2 是一個支援多語言的文本生成模型，適用於對話和文章創作。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
