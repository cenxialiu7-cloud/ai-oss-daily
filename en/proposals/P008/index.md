# 3D 電商素材工廠（一張商品照 → 3D 旋轉圖 + 展示影片）

賣家上傳一張商品照，自動產出可旋轉 3D 模型與展示短影片，做電商/AR 素材。

**Monetization**：①電商素材代製（按件）②素材訂閱站，下載頁掛 Adsterra/Monetag ③Shopify/蝦皮賣家工具。近日 3D 生成(TripoSplat/Pixal3D)爆發，市場剛起來。

**How it works**：商品照 → TripoSplat 轉 3D 高斯潑濺 → 輸出可旋轉模型/環景圖 → Bernini 生成展示短影片 → Lens/FLUX 補情境背景與材質、生多風格主圖 → 打包成賣家可直接上架的素材。

**Difficulty**：medium · **Effort**：3–4 週；3D 模型多為 Space/研究碼，需自架推理，難點在 3D 輸出格式與品質。

## Open-source parts

- [VAST-AI/TripoSplat](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/space-vast-ai-triposplat/) — · gradio, region:us
- [TencentARC/Pixal3D](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/space-tencentarc-pixal3d/) — · gradio, region:us
- [bytedance/Bernini](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/bytedance-bernini/) — Bernini is a unified framework for video generation and editing that combines an MLLM-based semantic planner …
