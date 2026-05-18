# PSSR

**Pixel-Level and Semantic-Level Adjustable Multi-Contrast MRI Super-Resolution via Context-Mixing Dynamic Kernels**
---

## Abstract

Multi-contrast MRI sequences provide complementary anatomical and pathological information for clinical diagnosis. However, long scanning time and physiological motion often lead to low-resolution target modal images. This paper proposes PSSR, a pixel-semantic dual-branch collaborative network for multi-contrast MRI super-resolution. The semantic branch explicitly decouples high-low frequency features via discrete wavelet transform (DWT), suppresses noise through semantic mixture (SE attention), and corrects cross-modal spatial offset via semantic alignment. The pixel branch adopts dual LoRA-driven dynamic convolution modules (DSPM) to model cross-modal correlations and generate adaptive kernels for detail reconstruction. A gradient reassignment strategy (GRS) routes auxiliary loss gradients directly to semantic blocks, alleviating gradient decay in deep dual-branch training.

---

## Quick Start

### Train

```bash
python main.py --model PSSR --dataset BraTSReg --upscale 4 --batch_size 8 --image_size 256
```

### Test

```bash
python val.py --model PSSR --dataset BraTSReg --upscale 4
```

### Dataset
- **BraTSReg** — Brain MRI (T1/T2)
- **IXI** — MRI (T1/T2)
- **CHAOS** — CT/MRI（跨域泛化测试）
