# LeafFormer | ICEBA 2026

LeafFormer là mô hình CNN–Transformer gọn nhẹ để phân loại tình trạng lá ổi, xoài và bưởi. Dự án nghiên cứu cách kết hợp đặc trưng cục bộ từ CNN với thông tin không gian rộng hơn từ Transformer trong một mô hình có khoảng **1,59 triệu tham số**.

## Thành quả tại ICEBA 2026

**Võ Duy Nhất** là đồng tác giả công trình *LeafFormer: An Adaptive CNN-Transformer For Parameter-Efficient Plant Leaf Disease Classification*. Công trình được trình bày theo hình thức **oral presentation** tại **ICEBA 2026, Vũng Tàu**, và được Ban tổ chức cấp **Certificate for Presentation**.

- **Mã bài và phiên:** 273 · Oral Session 7B.
- **Tác giả theo giấy chứng nhận:** Trần Văn Trung, Võ Duy Nhất, Phùng Bảo và Đỗ Minh Tiến.
- **Kết quả báo cáo tại hội nghị:** cấu hình LeafFormer dùng knowledge distillation (seed 42) đạt **97,37% accuracy** và **97,43% macro F1** trên bộ kiểm thử nội bộ gồm **1.254 ảnh**.

[Chương trình chính thức của hội nghị, bài O.S7B–273](https://www.iceba-conference.org/booklet-program_ICEBA2026.pdf#page=46) · [ICEBA 2026](https://www.iceba-conference.org/)

## LeafFormer hoạt động ra sao

```text
Ảnh lá → Encoder dùng chung → CNN và Transformer
→ Gate trộn đặc trưng theo từng ảnh → Phân loại 12 tình trạng lá
```

Hai nhánh dùng chung đặc trưng do encoder trích xuất. Gate tính mức đóng góp của từng nhánh theo ảnh đầu vào. Trong cấu hình có knowledge distillation, mô hình teacher hướng dẫn student khi huấn luyện. Khi suy luận chỉ cần student.

## Dữ liệu, mã nguồn và kết quả ICEBA

- **Dữ liệu dùng trong benchmark:** [GMP-Leaf12 đã chia train/validation/test trên Kaggle](https://www.kaggle.com/datasets/trung272004/data-leaf-disease-detection-15k). Trang Kaggle ghi 17.500 ảnh. Log nạp dữ liệu trong benchmark ghi 17.494 mẫu dùng trong thí nghiệm, gồm 15.000 train, 1.240 validation và 1.254 test. [Đối chiếu cách đếm trong README benchmark](https://github.com/tranvantrung27/GMP-Leaf12-Benchmark#gmp-leaf12-dataset).
- **Mã mô hình:** [Notebook LeafFormer](https://github.com/tranvantrung27/GMP-Leaf12-Benchmark/blob/main/proposed_model/LeafFormer.ipynb) trong [kho mã GMP-Leaf12-Benchmark của nhóm](https://github.com/tranvantrung27/GMP-Leaf12-Benchmark).
- **Kết quả:** [Báo cáo đánh giá LeafFormer (PDF)](https://github.com/tranvantrung27/GMP-Leaf12-Benchmark/blob/main/results/leafformer_report.pdf).
- **Ảnh gốc và ghi công:** Bộ ảnh do **Trần Văn Trung và Võ Duy Nhất** thực hiện và quản lý. [Bộ ảnh nguồn trên Kaggle](https://www.kaggle.com/datasets/trungbebong2704/leaf-disease-detection-ds) · [Giới thiệu và ảnh mẫu](https://github.com/tranvantrung27/leaf-disease-detection-DS).

## Các giai đoạn liên quan

- [LeafFormer Q3 · Các thí nghiệm nội bộ đã hoàn thành](https://github.com/vonhat204/leafformer-q3)
- [LeafFormer Q2 · Hướng nghiên cứu tiếp theo](https://github.com/vonhat204/leafformer-q2)
