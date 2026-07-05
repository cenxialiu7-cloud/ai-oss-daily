# AI 開發記憶與規格中樞：讓 Claude Code／Cursor 團隊每次開新 session 都不失憶、需求不跑偏

把每次 agent session 的上下文自動壓縮成長期記憶，並把口頭需求即時整理成正式規格，讓任何相容 client 接上就能『記得』專案。

**怎麼變現**：①Mac 本機工具買斷（個人開發者版：本機記憶庫＋規格產生器，資料不上雲）②團隊版 SaaS 月費（共享記憶庫＋規格庫，依席次計費，主打新創／外包 agency）③IDE／編輯器市集擴充功能上架抽成，另接 Ko-fi 贊助與工具／主機商聯盟（非 VPN）。行銷頁廣告只放網頁端 Adsterra／Monetag。

**運作方式**：claude-mem 攔截並壓縮每次 Claude Code／Cursor session 的對話與決策成持久記憶，跨會話載回省去重複解釋專案背景 → sudokar/openspec-plus 把記憶中浮現的口頭需求即時轉成結構化 Spec-Driven 規格文件，做需求發現與驗收條件管理，避免代理程式自己腦補導致需求跑偏 → DietrichGebert/ponytail 讓 agent 依懶惰開發者思維執行，搭配既有記憶與規格減少不必要的重複程式碼與探索步驟 → 全部透過 modelcontextprotocol/python-sdk 包成一個 MCP server，任何相容 client（Claude、Cursor、Windsurf、Copilot）掛上即可共用同一套記憶與規格層。與 P007（Skill 策展）、P021／P027（省 token／理解程式碼）不同：本案核心賣點是『跨會話記憶』與『需求規格化』，解決的是失憶與需求跑偏，不是技能管理或程式碼探索。

**難度**：medium · **投入估計**：2–3 週可做出 MVP：先做本機 SQLite 記憶庫＋規格轉換單機版，MCP server 包裝與多 client 相容測試再約 1 週；難點在記憶壓縮的取捨（留什麼丟什麼才不失真）與口頭需求轉規格的準確度。

## 用到的開源零件

- [thedotmack/claude-mem](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/thedotmack-claude-mem/) — Claude Agent 的持久上下文跨會話系統，捕獲並壓縮會話內容。
- [sudokar/openspec-plus](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/sudokar-openspec-plus/) — 增強 OpenSpec 的 Spec-Driven 開發，提供更好的發現、需求分析等功能。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
- [DietrichGebert/ponytail](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/dietrichgebert-ponytail/) — 讓AI代理程式以懶惰開發者的思維方式運作，減少程式碼編寫。
