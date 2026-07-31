# 團隊共用程式碼記憶 MCP（自架）：一次索引全公司程式碼，讓 Claude／Cursor／Codex 每個 AI 工具都精準檢索、程式碼零外流

把整個 codebase 建成一座自架的 MCP 索引，團隊任何 AI 編碼工具連上就能秒查『這功能在哪、怎麼串接、改哪裡會壞』，程式碼不出公司內網。

**Monetization**：①團隊自架授權＋席次月費（SaaS）：主打注重程式碼保密、不能上雲的團隊（金融／醫療／政府外包），依開發者席次或索引 repo 數計費；②個人開發者 Mac App 買斷（本機索引單機版，資料零外流）；③官網／文件站掛 Adsterra／Monetag 網頁廣告引流，放 Ko-fi 贊助，並接自架 VPS／主機商聯盟連結（自架需常駐索引節點）。廣告只放網頁端，絕不碰任何 VPN 類聯盟。

**How it works**：codebase-memory-mcp 對整個 repo／monorepo 做多語言快速索引，建立可語意檢索的程式碼記憶庫 → 透過 modelcontextprotocol/python-sdk 暴露成標準 MCP server，讓 Claude、Cursor、Codex、Windsurf、Gemini 等多個 AI client 連上『同一份』索引，不必各自重掃 → code-yeongyu/oh-my-openagent 負責在複雜 codebase 上做多步驟檢索與跨檔案追蹤（『這個函式誰在呼叫、改了會影響哪些頁面』）→ addyosmani/agent-skills 把檢索到的結果接上生產級工程技能，直接轉成重構、補測試、寫文件等具體動作 → 需要離線／隱私部署時，用 nvidia/Qwen3.6-35B-A3B-NVFP4（NVFP4 量化 MoE，省顯存）在自有主機上做推理，程式碼與查詢全程不出內網。與 P018（視覺化架構地圖）、P029（文件＋流程的企業 RAG 問答）、P037（跨會話對話記憶）定位不同：本案是專供 AI 編碼工具共用的『程式碼索引檢索後端』基礎設施，核心是多 client 共享同一份高速程式碼索引且可自架。

**Difficulty**：medium · **Effort**：估 2–3 週做出能跑的自架版：codebase-memory-mcp 索引＋python-sdk 暴露工具約 1 週，多 client（Claude／Cursor／Codex）相容測試與一鍵自架打包約 1 週；難點在大型 monorepo 的索引效能與增量更新、跨 client 的 MCP 相容性差異，以及自架部署（含本機模型）的資源需求與安裝體驗。

## Open-source parts

- [DeusData/codebase-memory-mcp](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/deusdata-codebase-memory-mcp/) — High-performance code intelligence MCP server. Indexes codebases into a persistent knowledge graph — average …
- [code-yeongyu/oh-my-openagent](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/code-yeongyu-oh-my-openagent/) — omo/lazycodex: The coding agent for tokenmaxxers;the one and only agent harness for complex codebases. For yo…
- [addyosmani/agent-skills](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/addyosmani-agent-skills/) — Production-grade engineering skills for AI coding agents.
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/modelcontextprotocol-python-sdk/) — The official Python SDK for Model Context Protocol servers and clients
- [nvidia/Qwen3.6-35B-A3B-NVFP4](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-nvidia-qwen3-6-35b-a3b-nvfp4/) — text-generation · Model Optimizer, safetensors, qwen3_5_moe
