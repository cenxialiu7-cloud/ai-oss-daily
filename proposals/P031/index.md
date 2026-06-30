# AI 瀏覽器 QA／網站體檢代理：丟網址或 PR → 真實瀏覽器走查＋效能錯誤報告，可擋合併

把一個網站或一個 PR 交給 AI，它用真實 Chrome 跑端對端流程、抓效能與主控台錯誤、定位受影響頁面，產出可擋下不良合併的健檢報告。

**怎麼變現**：①CI／CD 整合 SaaS 月費：每次合併自動跑瀏覽器走查＋效能與主控台錯誤監控，依專案數或執行次數計費②免費『單頁網站健檢』工具（網頁端，效能／錯誤報告）掛 Adsterra／Monetag 廣告引流③進階報告模板與導入顧問走 Ko-fi，推薦相容的瀏覽器測試雲與主機商走工具／主機商聯盟。絕不碰任何 VPN 類聯盟。

**運作方式**：open-code-review 解析 PR diff，判定改動風險與該重測範圍 → semble 對改動程式碼做高速語意檢索，定位受影響的頁面與元件（比 grep+read 省約 98% token）→ thClaws 當多供應商代理框架，把測試計畫排成可執行步驟並提供 GUI／CLI → chrome-devtools-mcp 驅動真實 Chrome 走查流程，擷取效能 trace、網路請求、主控台錯誤與截圖 → 彙整成附證據、可一鍵擋合併的健檢報告。

**難度**：high · **投入估計**：4–6 週做出能接 CI 的版本；難點在從 diff 自動推導穩定的瀏覽器測試步驟與重放、效能與錯誤判讀的誤報抑制，以及把報告做成可擋 PR 的閘門；核心皆為現成 MCP／工具。

## 用到的開源零件

- [ChromeDevTools/chrome-devtools-mcp](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/chromedevtools-chrome-devtools-mcp/) — 用於程式設計代理的Chrome開發者工具外掛。
- [alibaba/open-code-review](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/alibaba-open-code-review/) — 阿里巴巴規模下驗證的程式碼審查工具，結合確定性管道與 LLM 代理。
- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/minishlab-semble/) — 快速且精確的程式碼搜尋工具，比 grep+read 少用約 98% 的 token。
- [thClaws/thClaws](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/thclaws-thclaws/) — 開源AI代理框架，提供GUI、CLI等多種介面，支援多供應商。
