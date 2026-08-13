# ETF 相對強度輪動研究台：系統化排名強勢 ETF、拆解超額報酬來源，本機自架、人來決策

一鍵掃描 ETF 宇宙的相對強度排名，拆解每檔的 alpha 歸因（因子貢獻），產出可下載的輪動研究報告——不推播訊號、不代下單，決定權留給使用者。

**Monetization**：①Mac App 買斷：本機研究台，價量資料在本機計算、零外流，一次付費適合重視隱私的散戶與獨立投資人；②Ko-fi 贊助解鎖進階報告模板與『每週 ETF 輪動榜』電子報；③券商／看盤軟體聯盟：研究台導流到開戶或數據方案（工具／服務類聯盟，非投顧、非代操）。公開的 ETF 輪動榜單網頁掛 Adsterra／Monetag 廣告衝自然流量。絕不碰任何 VPN 類聯盟，也不提供下單功能。

**How it works**：以 shoal-rat/quant-research-lab 當研究工作流骨架，排程抓取 ETF 價量資料與計算流程 → systematic-etf-relative-strength-alpha-attribution 計算各 ETF 的相對強度排名並做 alpha 歸因（把超額報酬拆成因子貢獻），找出當期強勢輪動族群 → sher1096/klinepic-agent-api-examples 為每檔入選 ETF 產出 K 線圖與強度走勢圖，插入報告 → 用 modelcontextprotocol/python-sdk 把整套包成一個 MCP server，讓 Claude／Cursor 一句話跑『本週 ETF 輪動研究』並取回繁中 HTML／PDF 報告。與 P003（泛用 vibe-trading 研究台）、P010（訊號推播服務）、P034（個股 AI 投委會）定位不同：本案專攻 ETF 相對強度／輪動與 alpha 歸因這一套方法論，客群是做 ETF 輪動配置的投資人，且明確定位為研究工具而非投顧。

**Difficulty**：medium · **Effort**：估 2–3 週做出能跑版本：quant-research-lab 工作流串接與資料源接入約 1 週，相對強度排名＋alpha 歸因計算與驗證約 1 週，K 線圖產出與報告排版約 0.5 週。難點在 ETF 價量／成分資料的穩定取得與速率限制、alpha 歸因因子模型的正確性驗證，以及措辭上必須清楚定位為研究工具、避免看起來像投顧訊號。

## Open-source parts

- [wenqi9115-glitch/systematic-etf-relative-strength-alpha-attribution](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/wenqi9115-glitch-systematic-etf-relative-strength-alpha-attribution/) — Systematic ETF relative-strength research, overlapping-sleeve portfolio construction, LEAN implementation, an…
- [shoal-rat/quant-research-lab](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/shoal-rat-quant-research-lab/) — An autonomous anime quant research office — chibi researchers hunt for alpha behind deflated-Sharpe gates whi…
- [sher1096/klinepic-agent-api-examples](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/sher1096-klinepic-agent-api-examples/) — Tested MCP server, one-click MCPB bundle, Docker image, and OpenAPI examples for turning broker or exchange f…
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/modelcontextprotocol-python-sdk/) — The official Python SDK for Model Context Protocol servers and clients
