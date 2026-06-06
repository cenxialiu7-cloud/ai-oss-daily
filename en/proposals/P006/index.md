# 隱私版・本機文件智能 App（Mac，發票/合約/名片秒抽欄位）

拖入文件，全程在本機 OCR＋結構化抽取＋摘要，資料不上雲——主打隱私的 Mac 生產力工具。

**Monetization**：①Mac App 買斷或訂閱 ②設定頁放 Ko-fi。屬『隱私/安全工具』類，絕不嵌第三方追蹤，完全契合你 MacSentinel 的定位與 Sparkle/notarize 發版 SOP。

**How it works**：拖入發票/合約/名片/報表 → PaddleOCR-VL 辨識 → NuExtract 抽成結構化欄位 → 本機 Qwen GGUF 摘要/翻譯 → 匯出 CSV/JSON。全程離線、零雲端、保隱私。

**Difficulty**：high · **Effort**：4–6 週（含 Mac App 殼與 Sparkle 自動更新）。

## Open-source parts

- [PaddlePaddle/PaddleOCR-VL-1.6](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-paddlepaddle-paddleocr-vl-1-6/) — image-text-to-text · PaddleOCR, safetensors, paddleocr_vl
- [numind/NuExtract3](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-numind-nuextract3/) — image-to-text · transformers, safetensors, image-text-to-text
- [Kwai-Keye/Keye-VL-2.0-30B-A3B](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-kwai-keye-keye-vl-2-0-30b-a3b/) — image-text-to-text · transformers, safetensors, KeyeVL2
- [unsloth/Qwen3.6-27B-MTP-GGUF](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-unsloth-qwen3-6-27b-mtp-gguf/) — image-text-to-text · transformers, gguf, unsloth
