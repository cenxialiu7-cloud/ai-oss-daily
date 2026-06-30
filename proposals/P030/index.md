# 網文小說 AI 寫作工作室：掃榜選題 → 拆解大綱 → 長文生成 → 一鍵有聲書

給網文寫手的一站式工具：自動掃榜找熱門題材、拆解爆款結構生成大綱、長篇逐章生成並去 AI 味，完稿再一鍵轉多角色有聲書。

**怎麼變現**：①寫手訂閱制 SaaS（月費）：掃榜選題＋拆文大綱＋長文生成＋去 AI 味＋人物世界觀聖經管理，按字數或專案計費②有聲書加值：用 MOSS-TTS 把章節轉多角色語音，賣有聲版產出或代製配音③免費『網文趨勢掃榜站』（網頁端）掛 Adsterra／Monetag 廣告引流，進階模板與抖內走 Ko-fi。絕不碰任何 VPN 類聯盟。

**運作方式**：oh-story-claudecode 提供掃榜／拆文／去 AI 味的網文寫作工作流骨架 → GLM-5.2 當中文長文寫作引擎，依拆解出的大綱逐章產出 → claude-obsidian 把人物設定、世界觀、伏筆整理成自組織知識圖譜（章節聖經），維持長篇前後一致 → 完稿章節丟 MOSS-TTS 轉多角色旁白輸出有聲書。全流程可本機或私有部署。

**難度**：medium · **投入估計**：3–4 週做出可用版本；模型與技能包現成，難點在長篇一致性（角色／伏筆記憶）的章節聖經串接與去 AI 味後處理，計費與前端為次要工。

## 用到的開源零件

- [worldwonderer/oh-story-claudecode](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/worldwonderer-oh-story-claudecode/) — 網文寫作技能包，涵蓋掃榜、拆文、去 AI 味道等全流程。
- [zai-org/GLM-5.2](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-zai-org-glm-5-2/) — GLM-5.2 是一個支援多語言的文本生成模型，適用於對話和文章創作。
- [MOSS-TTS v1.5（開源語音合成）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-openmoss-team-moss-tts-v1-5/) — 復旦 MOSS 團隊的開源 TTS 模型（pipeline: text-to-speech）。
- [AgriciDaniel/claude-obsidian](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/agricidaniel-claude-obsidian/) — Obsidian + Claude Code自組織AI第二大腦，協助管理知識圖譜。
