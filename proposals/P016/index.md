# 口播工廠 Pro（MediaGrab 素材 → 帶人聲口播的雙語短影音流水線）

把 MediaGrab（跨平台影音下載）當素材入口，串開源 TTS 與技能包標準，做成『丟一個選題或一支來源影片 → 自動產出帶配音、字幕、封面的雙語短影音』的可重現流水線。

**怎麼變現**：①桌面工具買斷（MoR：Gumroad/Lemon Squeezy 賣 macOS App，複用 Swift/SwiftUI/Sparkle/notarize 發版 SOP）＋進階模板訂閱 ②自營流量帳號接帶貨/聯盟（工具、主機商開戶，非 VPN）③落地頁 footer 放 Adsterra/Monetag 與 Ko-fi。

**運作方式**：MediaGrab 下載來源影音 → nemotron ASR 轉逐字稿做字幕與切點 → 一句選題或腳本經 openmelon runtime 編排，skillplus 技能包逐步：MOSS-TTS 生口播語音 → 對齊字幕 → html-anything 批量出封面圖卡 → 合成成品短影音。整條跑在本機，零雲端 API 費；技能包標準讓每步可替換、可重現、可賣模板。

**難度**：medium · **投入估計**：2–3 週（MediaGrab 已能下載，主要新工作是 ASR→TTS→封面 的 skillplus 技能編排與成品合成；先 CLI/pipeline MVP，再包 macOS App 用既有發版 SOP）。

## 用到的開源零件

- [openmelon（多模態內容創作 runtime）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/eight-acres-lab-openmelon/) — 可重現的多模態內容創作 agent 執行環境。
- [skillplus（可編譯技能包標準）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/eight-acres-lab-skillplus/) — 可編譯的技能包標準，用於打造可靠的內容生成 agent。
- [MOSS-TTS v1.5（開源語音合成）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-openmoss-team-moss-tts-v1-5/) — 復旦 MOSS 團隊的開源 TTS 模型（pipeline: text-to-speech）。
- [nvidia/nemotron-3.5-asr-streaming-0.6b](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-nvidia-nemotron-3-5-asr-streaming-0-6b/) — 即時語音識別系統，支援多語言。
- [nexu-io/html-anything](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/nexu-io-html-anything/) — 本地 AI 最佳化 HTML 編輯器，支援多種設計表面。
