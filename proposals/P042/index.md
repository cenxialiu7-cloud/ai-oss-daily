# 事件預測市場研究台：把全球即時新聞轉成機率，對照 Polymarket 賠率找錯價（本機自架，人來下決定）

worldmonitor 抓地緣政治／新聞事件 → LLM 估算事件真實機率 → 對照預測市場當下賠率，自動標出「市場錯價」清單，並用 riskguard 的倉位上限與熔斷規則守住風險。

**怎麼變現**：①Mac App 買斷：本機研究台，使用者自帶 API key，資料與策略不出機；②SaaS 月費：雲端版每日推送「事件錯價掃描報告」＋歷史校準分數（模型過去估得準不準），高階方案開放自訂事件追蹤；③免費的公開賠率／新聞追蹤網頁掛 Adsterra／Monetag 網頁廣告引流，站上放 Ko-fi 贊助與自架 VPS／主機商聯盟連結（自架者需要跑 24 小時監控節點）。定位是研究與風控工具，不代客下單、不做包贏承諾。

**運作方式**：koala73/worldmonitor 當即時情報層，持續聚合新聞與地緣政治訊號 → OpenOSINT 針對特定事件主體（人物／公司／國家）補齊公開背景情報 → hf:model:zai-org/GLM-5.2 本機或自架推論，把「事件敘述＋背景卷宗」轉成帶信心區間的機率估計與理由摘要 → MalcolmMcGough/polymarket-trading-bot-scalping 與 ale2348/trading-bot 提供 Polymarket 的行情擷取與下單介面（本案只取其「讀盤／賠率擷取」與可選的半自動執行層），把估計機率對照市場隱含機率算出錯價幅度 → SilentFleetKK/riskguard 作為執行前的風控閘門，套用倉位上限、單日最大虧損與熔斷機制。所有錯價候選以清單呈現給人審核，預設不自動下單。與 P010（股票／加密訊號社群）、P034（個股決策報告）、P038（MT5 風控）皆不同市場、不同資料源：本案吃的是新聞事件與預測市場賠率。

**難度**：high · **投入估計**：估 4–6 週做出能跑的 MVP：worldmonitor 事件流接入＋事件正規化約 1.5 週，LLM 機率估計與提示工程約 1.5 週，Polymarket 賠率擷取與錯價比對約 1 週，riskguard 風控與回顧校準（Brier score）約 1–2 週。難點在事件與市場合約的對齊（同一事件在市場上的措辭與結算條件常不同）、LLM 機率的校準與過度自信、以及低流動性合約的滑價。

## 用到的開源零件

- [koala73/worldmonitor](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/koala73-worldmonitor/) — 即時全球情報儀錶板，整合新聞聚合、地緣政治監控等功能。
- [MalcolmMcGough/polymarket-trading-bot-scalping](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/malcolmmcgough-polymarket-trading-bot-scalping/) — 用於Polymarket超短期市場的自動化交易機器人。
- [ale2348/trading-bot](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/ale2348-trading-bot/) — 用於Polymarket五分鐘加密貨幣市場的自動化交易機器人。
- [SilentFleetKK/riskguard](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/silentfleetkk-riskguard/) — 交易風險控制層，提供倉位上限、熔斷機制等核心功能，無外部依賴。
- [OpenOSINT/OpenOSINT](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/openosint-openosint/) — 結合16種工具的AI驅動情報收集代理程式，支援Claude、GPT-4等模型。
- [zai-org/GLM-5.2](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-zai-org-glm-5-2/) — GLM-5.2 是一個支援多語言的文本生成模型，適用於對話和文章創作。
