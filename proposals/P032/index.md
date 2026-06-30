# 本機法律 AI 工作台：合約審閱、法規檢索、文件起草一站搞定（Mac App，多司法管轄）

把開源法律技能庫＋OCR＋本機 LLM 串成個人律師與中小企業法務的合約審閱、檢索與起草助手，敏感卷宗完全不出本機。

**怎麼變現**：①Mac App 買斷（個人律師／法務單機版），多司法管轄擴充包與條款範本庫加購；②小型事務所 SaaS 月費（多人協作、案件庫雲端同步、版本留痕）；③公開行銷站掛 Adsterra／Monetag 網頁廣告引流，另開 Ko-fi 贊助與法規模板訂閱。主打『卷宗零外流』隱私賣點，絕不碰任何 VPN 類聯盟。

**運作方式**：上傳或掃描的合約／判決先用 Unlimited-OCR 轉文字入庫 → semble 建立本機語意索引做秒級條文檢索（比 grep+read 省約 98% token）→ legal-skills-open 提供多司法管轄的條款審閱、風險標註與起草範本技能，透過 modelcontextprotocol/python-sdk 包成 MCP server 供 Claude／Cursor 或內建 GLM-5.2 本機模型呼叫 → 輸出帶條款引用與修改建議的審閱報告，全程於 Mac 端離線運算。

**難度**：high · **投入估計**：可跑 MVP 約 4–6 週：OCR→索引→技能呼叫管線一週可通，難點在多司法管轄的法規對應正確性、條款風險判讀可靠度，以及免責聲明與責任邊界設計；本機 LLM 起草品質需反覆校調。

## 用到的開源零件

- [ThomasMoreAI/legal-skills-open](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/thomasmoreai-legal-skills-open/) — 開源法律AI技能庫，支援多個司法管轄區和MCP相容代理機器人。
- [baidu/Unlimited-OCR](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-baidu-unlimited-ocr/) — 百度的無限 OCR 技術，將影像轉換為文字。
- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/minishlab-semble/) — 快速且精確的程式碼搜尋工具，比 grep+read 少用約 98% 的 token。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
- [zai-org/GLM-5.2](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-zai-org-glm-5-2/) — GLM-5.2 是一個支援多語言的文本生成模型，適用於對話和文章創作。
