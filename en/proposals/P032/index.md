# 本機法律 AI 工作台：合約審閱、法規檢索、文件起草一站搞定（Mac App，多司法管轄）

把開源法律技能庫＋OCR＋本機 LLM 串成個人律師與中小企業法務的合約審閱、檢索與起草助手，敏感卷宗完全不出本機。

**Monetization**：①Mac App 買斷（個人律師／法務單機版），多司法管轄擴充包與條款範本庫加購；②小型事務所 SaaS 月費（多人協作、案件庫雲端同步、版本留痕）；③公開行銷站掛 Adsterra／Monetag 網頁廣告引流，另開 Ko-fi 贊助與法規模板訂閱。主打『卷宗零外流』隱私賣點，絕不碰任何 VPN 類聯盟。

**How it works**：上傳或掃描的合約／判決先用 Unlimited-OCR 轉文字入庫 → semble 建立本機語意索引做秒級條文檢索（比 grep+read 省約 98% token）→ legal-skills-open 提供多司法管轄的條款審閱、風險標註與起草範本技能，透過 modelcontextprotocol/python-sdk 包成 MCP server 供 Claude／Cursor 或內建 GLM-5.2 本機模型呼叫 → 輸出帶條款引用與修改建議的審閱報告，全程於 Mac 端離線運算。

**Difficulty**：high · **Effort**：可跑 MVP 約 4–6 週：OCR→索引→技能呼叫管線一週可通，難點在多司法管轄的法規對應正確性、條款風險判讀可靠度，以及免責聲明與責任邊界設計；本機 LLM 起草品質需反覆校調。

## Open-source parts

- [ThomasMoreAI/legal-skills-open](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/thomasmoreai-legal-skills-open/) — Open library of legal AI skills (SKILL.md) for MCP-compatible agents — 39 jurisdictions, 200+ plugins, Apache…
- [baidu/Unlimited-OCR](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-baidu-unlimited-ocr/) — image-text-to-text · transformers, safetensors, unlimited-ocr
- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/minishlab-semble/) — Fast and Accurate Code Search for Agents. Uses ~98% fewer tokens than grep+read
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/modelcontextprotocol-python-sdk/) — The official Python SDK for Model Context Protocol servers and clients
- [zai-org/GLM-5.2](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-zai-org-glm-5-2/) — text-generation · transformers, safetensors, glm_moe_dsa
