# LeafFormer | ICEBA 2026 và nghiên cứu mở rộng

LeafFormer là mô hình CNN–Transformer gọn nhẹ để phân loại tình trạng lá ổi, xoài và bưởi. Dự án nghiên cứu cách kết hợp đặc trưng cục bộ từ CNN với thông tin không gian rộng hơn từ Transformer trong một mô hình có khoảng **1,59 triệu tham số**.

## Thành quả tại ICEBA 2026

**Võ Duy Nhất** là đồng tác giả công trình *LeafFormer: An Adaptive CNN-Transformer For Parameter-Efficient Plant Leaf Disease Classification*. Công trình được trình bày theo hình thức **oral presentation** tại **ICEBA 2026, Vũng Tàu**, và được Ban tổ chức cấp **Certificate for Presentation**.

- **Mã bài và phiên:** 273 · Oral Session 7B.
- **Tác giả theo giấy chứng nhận:** Trần Văn Trung, Võ Duy Nhất, Phùng Bảo và Đỗ Minh Tiến.
- **Kết quả báo cáo tại hội nghị:** cấu hình LeafFormer dùng knowledge distillation (seed 42) đạt **97,37% accuracy** và **97,43% macro F1** trên bộ kiểm thử nội bộ gồm **1.254 ảnh**.

[Chương trình chính thức của hội nghị, bài O.S7B–273](https://www.iceba-conference.org/booklet-program_ICEBA2026.pdf#page=47) · [ICEBA 2026](https://www.iceba-conference.org/)

## LeafFormer hoạt động ra sao

```text
Ảnh lá → Encoder dùng chung → CNN và Transformer
→ Gate trộn đặc trưng theo từng ảnh → Phân loại 12 tình trạng lá
```

Hai nhánh dùng chung đặc trưng do encoder trích xuất. Gate tính mức đóng góp của từng nhánh theo ảnh đầu vào. Trong cấu hình có knowledge distillation, mô hình teacher hướng dẫn student khi huấn luyện. Khi suy luận chỉ cần student.

## Bản mở rộng Q3

**Trạng thái:** đã hoàn thành các thí nghiệm so sánh nội bộ dưới đây và chuẩn bị bản thảo mở rộng. Tác giả bản thảo hiện tại gồm **Võ Duy Nhất, Phùng Bảo và Đỗ Minh Tiến**.

- Rà soát **8.370 ảnh thuộc 12 lớp** và xây dựng quy trình đánh giá thống nhất. Có **18 checkpoint** được chọn theo validation và khóa trước khi chấm trên test nội bộ.
- So sánh trộn thích ứng, lấy trung bình, nối đặc trưng, các baseline và cấu hình có knowledge distillation qua nhiều seed.
- Đối chiếu độ chính xác với số tham số và tính khoảng tin cậy cho các so sánh ghép cặp. Kết quả nội bộ chưa cho thấy lợi ích nhất quán từ trộn thích ứng hoặc công thức distillation đã thử.
- Phân tích độ chồng lấp của vùng giải thích **LIME** với vùng tham chiếu trên checkpoint lịch sử. Phần này có phạm vi riêng với kết quả của 18 checkpoint mới.

## Nguồn dữ liệu và ghi công

Bộ **Leaf Disease Detection Dataset** do **Trần Văn Trung và Võ Duy Nhất** thực hiện và quản lý. Bộ dữ liệu công khai gồm ảnh lá ổi, xoài và bưởi ở trạng thái khỏe hoặc có bệnh. Thống kê và bộ chia của từng thí nghiệm LeafFormer được báo cáo theo từng giai đoạn.

[Xem dữ liệu trên Kaggle](https://www.kaggle.com/datasets/trungbebong2704/leaf-disease-detection-ds) · [README và ảnh mẫu do nhóm công bố](https://github.com/tranvantrung27/leaf-disease-detection-DS)
