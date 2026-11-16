# LeafFormer | ICEBA 2026

LeafFormer is a lightweight CNN–Transformer model for classifying the condition of guava, mango, and pomelo leaves. The project investigates how to combine local CNN features with broader spatial information from a Transformer in a model with approximately **1.59 million parameters**.

## ICEBA 2026 presentation

**Võ Duy Nhất** co-authored *LeafFormer: An Adaptive CNN-Transformer For Parameter-Efficient Plant Leaf Disease Classification*. The work was presented orally at **ICEBA 2026 in Vũng Tàu**, and the organizers issued a **Certificate for Presentation**.

- **Paper and session** — Paper 273, Oral Session 7B.
- **Authors listed on the certificate** — Trần Văn Trung, Võ Duy Nhất, Phùng Bảo, and Đỗ Minh Tiến.
- **Conference results** — LeafFormer with knowledge distillation (seed 42) achieved **97.37% accuracy** and **97.43% macro F1** on an internal test set of **1,254 images**.

[Official conference program, paper O.S7B–273](https://www.iceba-conference.org/booklet-program_ICEBA2026.pdf#page=46) · [ICEBA 2026](https://www.iceba-conference.org/)

## How LeafFormer works

```text
Leaf image → Shared encoder → CNN and Transformer branches
→ Image-dependent gated fusion → 12-class leaf condition prediction
```

Both branches use features from the shared encoder. The gate adjusts each branch’s contribution based on the input image. When knowledge distillation is enabled, a teacher guides the student during training. Inference uses the student alone.

## ICEBA dataset, source code, and results

- **Benchmark dataset** — [GMP-Leaf12 with train, validation, and test splits on Kaggle](https://www.kaggle.com/datasets/trung272004/data-leaf-disease-detection-15k). Kaggle lists 17,500 images. The benchmark data-loading logs record 17,494 samples used in the experiments, comprising 15,000 training, 1,240 validation, and 1,254 test samples. [See the count breakdown in the benchmark README](https://github.com/tranvantrung27/GMP-Leaf12-Benchmark#gmp-leaf12-dataset).
- **Model implementation** — [LeafFormer notebook](https://github.com/tranvantrung27/GMP-Leaf12-Benchmark/blob/main/proposed_model/LeafFormer.ipynb) in the [team’s GMP-Leaf12-Benchmark repository](https://github.com/tranvantrung27/GMP-Leaf12-Benchmark).
- **Results** — [LeafFormer evaluation report (PDF)](https://github.com/tranvantrung27/GMP-Leaf12-Benchmark/blob/main/results/leafformer_report.pdf).
- **Original images and attribution** — **Trần Văn Trung and Võ Duy Nhất** created and maintain the image collection. [Original image collection on Kaggle](https://www.kaggle.com/datasets/trungbebong2704/leaf-disease-detection-ds) · [Dataset overview and sample images](https://github.com/tranvantrung27/leaf-disease-detection-DS).

## Related work

- [LeafFormer Q3 · Completed internal experiments](https://github.com/vonhat204/leafformer-q3)
- [LeafFormer Q2 · Research roadmap](https://github.com/vonhat204/leafformer-q2)
