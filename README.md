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

## Nguồn dữ liệu và ghi công

Bộ **Leaf Disease Detection Dataset** do **Trần Văn Trung và Võ Duy Nhất** thực hiện và quản lý. Bộ dữ liệu công khai gồm ảnh lá ổi, xoài và bưởi ở trạng thái khỏe hoặc có bệnh. Thống kê và bộ chia của từng thí nghiệm LeafFormer được báo cáo theo từng giai đoạn.

[Xem dữ liệu trên Kaggle](https://www.kaggle.com/datasets/trungbebong2704/leaf-disease-detection-ds) · [README và ảnh mẫu do nhóm công bố](https://github.com/tranvantrung27/leaf-disease-detection-DS)

## Các giai đoạn liên quan

- [LeafFormer Q3 · Các thí nghiệm nội bộ đã hoàn thành](https://github.com/vonhat204/leafformer-q3)
- [LeafFormer Q2 · Hướng nghiên cứu tiếp theo](https://github.com/vonhat204/leafformer-q2)
