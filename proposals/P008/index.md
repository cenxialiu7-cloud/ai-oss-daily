# 3D 電商素材工廠（一張商品照 → 3D 旋轉圖 + 展示影片）

賣家上傳一張商品照，自動產出可旋轉 3D 模型與展示短影片，做電商/AR 素材。

**怎麼變現**：①電商素材代製（按件）②素材訂閱站，下載頁掛 Adsterra/Monetag ③Shopify/蝦皮賣家工具。近日 3D 生成(TripoSplat/Pixal3D)爆發，市場剛起來。

**運作方式**：商品照 → TripoSplat 轉 3D 高斯潑濺 → 輸出可旋轉模型/環景圖 → Bernini 生成展示短影片 → Lens/FLUX 補情境背景與材質、生多風格主圖 → 打包成賣家可直接上架的素材。

**難度**：medium · **投入估計**：3–4 週；3D 模型多為 Space/研究碼，需自架推理，難點在 3D 輸出格式與品質。

## 用到的開源零件

- [VAST-AI/TripoSplat](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/space-vast-ai-triposplat/) — VAST AI TripoSplat：圖像轉 3D 高斯潑濺(3DGS)線上示範。
- [TencentARC/Pixal3D](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/space-tencentarc-pixal3d/) — 騰訊 ARC Pixal3D 3D 生成線上示範。
- [bytedance/Bernini](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/bytedance-bernini/) — 字節 Bernini：結合多模態 LLM 的統一影片生成與編輯框架。
