# 隱私版・本機文件智能 App（Mac，發票/合約/名片秒抽欄位）

拖入文件，全程在本機 OCR＋結構化抽取＋摘要，資料不上雲——主打隱私的 Mac 生產力工具。

**怎麼變現**：①Mac App 買斷或訂閱 ②設定頁放 Ko-fi。屬『隱私/安全工具』類，絕不嵌第三方追蹤，完全契合你 MacSentinel 的定位與 Sparkle/notarize 發版 SOP。

**運作方式**：拖入發票/合約/名片/報表 → PaddleOCR-VL 辨識 → NuExtract 抽成結構化欄位 → 本機 Qwen GGUF 摘要/翻譯 → 匯出 CSV/JSON。全程離線、零雲端、保隱私。

**難度**：high · **投入估計**：4–6 週（含 Mac App 殼與 Sparkle 自動更新）。

## 用到的開源零件

- [PaddlePaddle/PaddleOCR-VL-1.6](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-paddlepaddle-paddleocr-vl-1-6/) — 百度 PaddleOCR-VL 視覺語言 OCR 模型。
- [numind/NuExtract3](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-numind-nuextract3/) — NuExtract 結構化資訊抽取多模態模型（從文件/圖抽欄位）。
- [Kwai-Keye/Keye-VL-2.0-30B-A3B](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-kwai-keye-keye-vl-2-0-30b-a3b/) — 快手 Keye-VL 2.0 視覺語言模型（30B MoE，看圖理解）。
- [Unsloth 版 Qwen3.6-27B（GGUF 量化）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-unsloth-qwen3-6-27b-mtp-gguf/) — 由 Unsloth 釋出的 Qwen3.6-27B GGUF 量化權重，下載近 88 萬。
