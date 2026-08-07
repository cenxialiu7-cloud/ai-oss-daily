# AI 電影級產品宣傳片工作室：一張產品照＋賣點 → 電影感廣告短片

給電商／DTC 品牌的產品廣告片產線：上傳產品照與賣點，用電影級分鏡模板自動生成帶運鏡、旁白、字幕的宣傳短片，不必找攝影棚與剪接師。

**Monetization**：①品牌／賣家宣傳片代製接案（單支產品廣告片計費，或月方案包數支）；②模板與 prompt 包販售（video-shotcraft 分鏡模板＋產片工作流），賣給想自製的團隊；③打包成 Mac App 買斷給賣家自助產片，作品集／範例網站掛 Adsterra／Monetag 廣告引流、放 Ko-fi。廣告只放網頁端，絕不碰任何 VPN 類聯盟。

**How it works**：上傳產品照與賣點文案 → video-shotcraft（Claude／Codex 影片技能）依電影級產品宣傳片模板產生分鏡腳本與運鏡設計 → microsoft/Mage-Flow 生成／去背／編輯產品主視覺與場景畫面（rectified flow，可精修）、lodestones/Kroma 產出不同風格與場景變體 → Audio8/Audio8-TTS-Preview-0.6b 以自訂音色生成旁白配音 → 技能自動把畫面、運鏡、旁白、字幕依模板節奏串成成片 → 匯出直式／方形／橫式多平台比例版本。與 P001（衝流量的量產短影音）、P016（把既有素材配口播）、P022（靜態商用主圖）定位不同：本案專做『產品電影級廣告片』這種高單價 B2B 交付。

**Difficulty**：medium · **Effort**：估 2–3 週做出能跑的產片 pipeline：video-shotcraft 模板串接與腳本→分鏡約 1 週，Mage-Flow／Kroma 產品視覺與場景生成約 0.5–1 週，TTS 旁白＋自動剪接上字幕成片約 1 週。難點在分鏡→運鏡→剪接的自動串接品質與品牌一致性（同一支片的視覺風格要穩），模型與技能皆現成。

## Open-source parts

- [Vincentwei1021/video-shotcraft](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/vincentwei1021-video-shotcraft/) — AI video skill for Claude Code & Codex — cinematic product videos with Remotion: 106 shot recipe cards, 161 m…
- [microsoft/Mage-Flow](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-microsoft-mage-flow/) — text-to-image · diffusers, safetensors, text-to-image
- [lodestones/Kroma](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-lodestones-kroma/) — text-to-image · lora, krea2, krea
- [Audio8/Audio8-TTS-Preview-0.6b](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-audio8-audio8-tts-preview-0-6b/) — text-to-speech · transformers, safetensors, arktts
