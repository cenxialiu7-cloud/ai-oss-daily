# AI 瀏覽器 QA／網站體檢代理：丟網址或 PR → 真實瀏覽器走查＋效能錯誤報告，可擋合併

把一個網站或一個 PR 交給 AI，它用真實 Chrome 跑端對端流程、抓效能與主控台錯誤、定位受影響頁面，產出可擋下不良合併的健檢報告。

**Monetization**：①CI／CD 整合 SaaS 月費：每次合併自動跑瀏覽器走查＋效能與主控台錯誤監控，依專案數或執行次數計費②免費『單頁網站健檢』工具（網頁端，效能／錯誤報告）掛 Adsterra／Monetag 廣告引流③進階報告模板與導入顧問走 Ko-fi，推薦相容的瀏覽器測試雲與主機商走工具／主機商聯盟。絕不碰任何 VPN 類聯盟。

**How it works**：open-code-review 解析 PR diff，判定改動風險與該重測範圍 → semble 對改動程式碼做高速語意檢索，定位受影響的頁面與元件（比 grep+read 省約 98% token）→ thClaws 當多供應商代理框架，把測試計畫排成可執行步驟並提供 GUI／CLI → chrome-devtools-mcp 驅動真實 Chrome 走查流程，擷取效能 trace、網路請求、主控台錯誤與截圖 → 彙整成附證據、可一鍵擋合併的健檢報告。

**Difficulty**：high · **Effort**：4–6 週做出能接 CI 的版本；難點在從 diff 自動推導穩定的瀏覽器測試步驟與重放、效能與錯誤判讀的誤報抑制，以及把報告做成可擋 PR 的閘門；核心皆為現成 MCP／工具。

## Open-source parts

- [ChromeDevTools/chrome-devtools-mcp](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/chromedevtools-chrome-devtools-mcp/) — Chrome DevTools for coding agents
- [alibaba/open-code-review](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/alibaba-open-code-review/) — Open-source & free — Battle-tested at Alibaba's scale. Hybrid architecture code review tool: deterministic pi…
- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/minishlab-semble/) — Fast and Accurate Code Search for Agents. Uses ~98% fewer tokens than grep+read
- [thClaws/thClaws](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/thclaws-thclaws/) — Open-source AI agent harness in native Rust — GUI, CLI, headless, and webapp from one binary. Multi-provider,…
