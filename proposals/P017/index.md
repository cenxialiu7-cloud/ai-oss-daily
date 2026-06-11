# 資安情報 MCP ＋ 桌面哨兵（綜效 MacSentinel）：給 Claude/Cursor 的即時 CVE/紅隊軍火庫

把 CVE 情報、滲透測試工具集接成 MCP server，讓 AI agent 一句話就查到最新漏洞、跑安全稽核，搭配本機桌面哨兵做持續監控。

**怎麼變現**：①MCP server 分級訂閱（免費查公開 CVE，付費解鎖紅隊工具編排＋每日漏洞情報推播；Gumroad/Lemon Squeezy MoR 訂閱）②macOS 桌面版買斷（複用 MacSentinel 的 Sparkle/notarize 發版 SOP，設定頁 Ko-fi）③企業安全稽核報告單買/顧問。不碰 VPN/AdSense。

**運作方式**：cve-mcp-server 拉即時漏洞情報＋pentest-ai 提供稽核工具集 → arkon 自託管知識中心彙整成可查詢層 → 用 python-sdk 暴露為分級 MCP 工具（查 CVE 免費／紅隊編排與每日情報付費）→ 使用者 Claude/Cursor 直接連線；桌面版把同情報接進 MacSentinel 式本機監控，發現高風險即推 Telegram/LINE。

**難度**：medium · **投入估計**：3 週（MCP server 串接＋分級授權閘門；桌面版沿用 MacSentinel 既有殼與發版 SOP）。

## 用到的開源零件

- [mukul975/cve-mcp-server](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/mukul975-cve-mcp-server/) — 為Claude提供21個API的安全情報工具集，涵蓋多種安全標準和資料來源。
- [0xSteph/pentest-ai](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/0xsteph-pentest-ai/) — Offensive-security MCP伺服器，包含205個工具、17種專業代理和60個SPA探測器。
- [nduckmink/arkon](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/nduckmink-arkon/) — 企業級AI知識中心，支援自託管和多模型接入。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
