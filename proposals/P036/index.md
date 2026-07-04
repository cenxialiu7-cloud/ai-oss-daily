# AI 投資盡職調查中樞：把『AI 投資委員會決策報告』疊上『公司背景 OSINT 盡調』，產出機構級投資盡調卷宗

投資前一次到位：13 位角色化 AI 分析師的基本面辯論決策，加上對該公司與經營層的公開背景與風險盡調，合成一份附佐證的繁中投資盡職調查卷宗。

**🧩 組合自**：[P034 AI 投資委員會：13 位角色化 AI 分析師研究＋辯論＋風控 → 一份可下載的個股決策報告（非訊號推播）](https://cenxialiu7-cloud.github.io/ai-oss-daily/proposals/P034/)、[P035 AI 企業盡職調查工作台：輸入公司／網域 → 自動彙整公開情報 → 產出風險與背景盡調報告](https://cenxialiu7-cloud.github.io/ai-oss-daily/proposals/P035/)

**怎麼變現**：①網頁端免費『單檔快篩卷宗』（精簡決策傾向＋公司公開風險提示）掛 Adsterra／Monetag 廣告引流；②完整投資盡調卷宗付費解鎖（辯論全文＋回測佐證＋背景風險旗標＋佐證連結）用 Ko-fi 一次性解鎖，或 SaaS 月費賣給天使投資人／小型基金／FA（多檔追蹤、每週重算重掃、PDF 匯出）；③行情數據商、看盤圖表工具、券商開戶工具聯盟分潤，自架版帶主機商聯盟。全程附投資免責與僅用公開資料聲明，絕不碰任何 VPN 類聯盟。

**運作方式**：沿用 P034 的多智能體辯論產出個股決策傾向與信心度，並用 shy3130/tickflow-stock-panel 對標的跑技術面選股與歷史回測補上量化佐證 → 疊加 P035 的 OpenOSINT，針對該公司與經營層蒐集公開背景（登記關聯、訴訟／裁罰新聞、品牌冒用、負面提及等）作為投資風險旗標 → semble 高速交叉檢索辯論記錄與背景情報、去重並對齊矛盾點（比 grep+read 省約 98% token）→ GLM-5.2 把『決策辯論＋回測佐證＋背景風險』合成一份繁中投資盡調卷宗，標註信心度與佐證連結 → modelcontextprotocol/python-sdk 包成 MCP／CLI，網頁端輸出可下載卷宗。與 P034 差異：本案在決策報告之外加掛公司／經營層的公開背景盡調層，形成投資前更完整的風險檢核。

**難度**：high · **投入估計**：估 4–6 週：在 P034 既有辯論管線上整合 P035 的 OSINT 背景層與統一卷宗排版各約兩週；難點在辯論結論與背景風險的一致性校驗、公開資料合規與投資免責雙重邊界、多來源佐證的可追溯性，以及多智能體＋OSINT 蒐集的成本與延遲控制。

## 用到的開源零件

- [OpenOSINT/OpenOSINT](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/openosint-openosint/) — 結合16種工具的AI驅動情報收集代理程式，支援Claude、GPT-4等模型。
- [shy3130/tickflow-stock-panel](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/shy3130-tickflow-stock-panel/) — 基於 TickFlow 的 A 股量化工作臺，提供選股、監控及回測功能。
- [zai-org/GLM-5.2](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-zai-org-glm-5-2/) — GLM-5.2 是一個支援多語言的文本生成模型，適用於對話和文章創作。
- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/minishlab-semble/) — 快速且精確的程式碼搜尋工具，比 grep+read 少用約 98% 的 token。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
