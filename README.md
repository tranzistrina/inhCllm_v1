# inhCllm_v1

Experimental Russian description-to-C model, 91,245,312 parameters, derived from inhLLm-V4 PR #34. Trained from scratch for 1024 updates on 1980 of 2200 program/description pairs; 220 held out. Vocabulary 8192, ByteLevel BPE.

## Original checkpoint

- Filename: inhCllm_v1.ckpt
- Native V3CKPT01 FP32 weights and FP32 AdamW state; no quantization or conversion.
- Size: 1094943812 bytes
- SHA-256: c1a5a4dcf0e2a282a64cf88bce90bde71947847e1540fd22dfe7ddf40b135fb3
- Status: exact copy verified on the training server. Binary weights and matching tokenizer have NOT been uploaded to this repository; do not treat this card as a downloadable checkpoint.

## Evaluation

Validation loss 1.514052, final training loss 0.951001. Of 30 outputs across greedy and two sampling settings, 10 compiled, none passed the functional checks (0/78 repeated test cases). This is an experimental baseline, not a reliable coding assistant.

Architecture: D768, 12 heads, 12 layers, FFN2048, vocab8192. See [training implementation](https://github.com/tranzistrina/inhLLm-V4/pull/34). The future Russian conversational model will have a separate tokenizer and checkpoint.
