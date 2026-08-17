# AI 程式碼治理稽核台：團隊導入 AI coding agent 後，誰改了什麼、哪段是 agent 寫的、風險在哪，一次講清楚

掛在既有 Git 流程旁邊，記錄每一次 AI agent 的改動來源與提示脈絡，再自動跑審查，產出可交付稽核長官／客戶的『AI 產出程式碼』風險報告。

**Monetization**：①團隊版 SaaS 月費（依 repo 數或席次計價）：自架或雲端皆可，賣點是 AI 改動的可稽核性與合規交付；②Mac App 買斷：單人／小團隊本機版，程式碼不外流；③開發工具與主機商聯盟：報告內建議的 CI、靜態掃描、代管服務自然導流；④公開的免費線上『AI 程式碼風險自評』小工具頁掛 Adsterra／Monetag 廣告衝自然流量，並放 Ko-fi 贊助入口。不涉及任何 VPN 類聯盟。

**How it works**：以 pacifio/atlas 當底層來源記錄：它專門為 AI 程式碼代理做原始碼控制，可追蹤每次 agent 修改並事後查詢，於是每個 commit 都能標註『人寫／agent 寫／哪個 agent、什麼指令下產生』→ 這些被標記的差異丟進 alibaba/open-code-review（阿里巴巴規模驗證、確定性管道＋LLM 代理的審查工具）跑審查，對 AI 產出的段落套用更嚴格的規則集（幻覺 API、未處理錯誤、複製貼上重複、缺測試）→ NanoNets/Graft 補上程式碼上下文理解，讓審查看得懂跨檔案關聯而非只看 diff → Egonex-AI/Understand-Anything 把 repo 轉成可互動的知識圖譜，讓稽核者點開任一風險段落即可回溯它牽動的模組 → 最外層用 modelcontextprotocol/python-sdk 包成 MCP server，讓 Claude／Cursor 直接問『這個 release 有多少比例是 AI 寫的、風險最高的三處在哪』，並輸出繁中稽核報告（HTML／PDF）。與 P031（瀏覽器 QA／網站體檢）定位不同：P031 檢查的是網站在真實瀏覽器的行為，本案檢查的是『程式碼的產出來源與合規性』；與 P021（砍 token 帳單）、P037（開發記憶與規格）、P045（團隊程式碼記憶檢索）也不同：那三案是提升 agent 生產力，本案賣的是導入 agent 之後的治理與舉證能力。

**Difficulty**：medium · **Effort**：估 4–5 週做出能跑版本：atlas 的 agent 改動追蹤接進既有 Git 流程約 1.5 週，open-code-review 管道客製 AI 專屬規則集約 1 週，Graft 上下文層與 Understand-Anything 知識圖譜整併約 1 週，MCP 包裝與報告輸出約 1 週。難點在於『這段是不是 agent 寫的』的歸因準確度（需在 agent 側就攔截記錄，事後推斷不可靠）、大型 repo 的圖譜建置效能，以及要讓報告的結論穩定到能拿去給稽核／客戶看，不能每次跑都換一套說法。

## Open-source parts

- [pacifio/atlas](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/pacifio-atlas/) — Source control for agents. Use multiple coding agents, track their changes and query them in one place
- [alibaba/open-code-review](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/alibaba-open-code-review/) — Fast, efficient, battle-tested at Alibaba's scale. Hybrid architecture code review tool: deterministic pipeli…
- [NanoNets/Graft](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/nanonets-graft/) — Turbocharge Claude Code, Cursor, Codex, Gemini & every coding agent: faster, cheaper, with contextual underst…
- [Egonex-AI/Understand-Anything](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/egonex-ai-understand-anything/) — Graphs that teach > graphs that impress. Turn any code into an interactive knowledge graph you can explore, s…
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/modelcontextprotocol-python-sdk/) — The official Python SDK for Model Context Protocol servers and clients
