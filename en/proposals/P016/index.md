# 口播工廠 Pro（MediaGrab 素材 → 帶人聲口播的雙語短影音流水線）

把 MediaGrab（跨平台影音下載）當素材入口，串開源 TTS 與技能包標準，做成『丟一個選題或一支來源影片 → 自動產出帶配音、字幕、封面的雙語短影音』的可重現流水線。

**Monetization**：①桌面工具買斷（MoR：Gumroad/Lemon Squeezy 賣 macOS App，複用 Swift/SwiftUI/Sparkle/notarize 發版 SOP）＋進階模板訂閱 ②自營流量帳號接帶貨/聯盟（工具、主機商開戶，非 VPN）③落地頁 footer 放 Adsterra/Monetag 與 Ko-fi。

**How it works**：MediaGrab 下載來源影音 → nemotron ASR 轉逐字稿做字幕與切點 → 一句選題或腳本經 openmelon runtime 編排，skillplus 技能包逐步：MOSS-TTS 生口播語音 → 對齊字幕 → html-anything 批量出封面圖卡 → 合成成品短影音。整條跑在本機，零雲端 API 費；技能包標準讓每步可替換、可重現、可賣模板。

**Difficulty**：medium · **Effort**：2–3 週（MediaGrab 已能下載，主要新工作是 ASR→TTS→封面 的 skillplus 技能編排與成品合成；先 CLI/pipeline MVP，再包 macOS App 用既有發版 SOP）。

## Open-source parts

- [eight-acres-lab/openmelon](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/eight-acres-lab-openmelon/) — A content-creation agent runtime for reproducible multimodal production — projects, workflows, skills, proven…
- [eight-acres-lab/skillplus](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/eight-acres-lab-skillplus/) — A compilable skill package standard for reliable content-generation agents.
- [OpenMOSS-Team/MOSS-TTS-v1.5](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-openmoss-team-moss-tts-v1-5/) — text-to-speech · safetensors, moss_tts_delay, text-to-speech
- [nvidia/nemotron-3.5-asr-streaming-0.6b](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-nvidia-nemotron-3-5-asr-streaming-0-6b/) — automatic-speech-recognition · nemo, speech-recognition, cache-aware ASR
- [nexu-io/html-anything](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/nexu-io-html-anything/) — ✨ The agentic HTML editor — your local AI agent writes the HTML, you ship it. 🚀 75 Skills × 9 Surfaces (magaz…
