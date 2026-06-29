# 企業私有 AI 知識中樞（自架 RAG）：文件＋程式碼＋工作記憶餵進私有 LLM，一問就找到

把公司散落的文件、程式碼、流程知識灌進一個自架的 AI 大腦，員工用一句話問答就能找到任何答案——資料完全不出公司內網。

**Monetization**：①自架授權＋建置顧問費（幫中小企業／事務所／診所導入，一次性收費）②月維護與模型更新訂閱（SaaS 按席次月費）③加值：接 LINE／Slack 內部問答機器人。行銷頁掛 Adsterra／Monetag、放 Ko-fi；主打『資料零外流』隱私賣點，不碰需上傳雲端的方案。

**How it works**：arkon 當企業知識中樞與多模型路由 → Unlimited-OCR 把紙本／PDF／掃描件轉文字入庫 → semble 對文件與程式碼做高速語意檢索（比 grep+read 省約 98% token）→ holaOS 記住每個專案／員工的工作上下文 → GLM-5.2 當本機或私有部署的 LLM 產生帶出處引用的答案。全套可自架，資料不出內網。

**Difficulty**：high · **Effort**：4–6 週做出可導入的 MVP；難點在多來源資料管線（OCR／程式碼／文件統一入庫）、權限隔離與一鍵部署打包，模型與核心元件皆現成。

## Open-source parts

- [nduckmink/arkon](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/nduckmink-arkon/) — Arkon: Enterprise AI Knowledge Hub & MCP Server. Self-hosted knowledge base for teams to manage RAG contexts,…
- [holaboss-ai/holaOS](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/holaboss-ai-holaos/) — Your super agent for work: local-first, learn your working context in mins and never forget it.
- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/minishlab-semble/) — Fast and Accurate Code Search for Agents. Uses ~98% fewer tokens than grep+read
- [baidu/Unlimited-OCR](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-baidu-unlimited-ocr/) — image-text-to-text · transformers, safetensors, unlimited-ocr
- [zai-org/GLM-5.2](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-zai-org-glm-5-2/) — text-generation · transformers, safetensors, glm_moe_dsa
