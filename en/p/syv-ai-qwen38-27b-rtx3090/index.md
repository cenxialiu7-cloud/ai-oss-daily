# syv-ai/qwen38-27b-rtx3090

Qwen3.8-27B on a single RTX 3090 with vLLM: ~1,000 tok/s at 64 concurrent (int8 tensor-core GEMMs, fp16 DeltaNet state), ~114 tok/s single-user at default sampling / ~124 greedy (MTP drafts, own-output draft vocab, calibrated int4 lm_head, split-KV verify attention), 150k-262k context; patches, requant scripts, benchmarks

**Commercial license**：Commercial OK — 可商用，通常只需保留著作權聲明/授權條款

**Stars**：380
**Source**：https://github.com/syv-ai/qwen38-27b-rtx3090
