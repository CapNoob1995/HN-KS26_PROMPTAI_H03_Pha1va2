# BÀI LÀM PHA 2 (ĐỀ LUYỆN TẬP CHỦ ĐỀ TÀI CHÍNH CÁ NHÂN)

- **Họ tên:** Bùi Quang Huy
- **Lớp:** HN-KS26-CNTT3
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đăng ký hội thảo ra JSON

**KET QUA AI**

```text
[
  {
    "ma_goi": "DT",
    "ngay_hoi_thao": "2026-12-20",
    "nguoi_lon": 2,
    "tre_em": 1,
    "hang_ve": "thuong",
    "ghi_chu": null
  },
  {
    "ma_goi": "CB",
    "ngay_hoi_thao": "2027-01-10",
    "nguoi_lon": 3,
    "tre_em": 0,
    "hang_ve": null,
    "ghi_chu": "một người dùng xe lăn cần lối đi riêng"
  },
  {
    "ma_goi": "VIP",
    "ngay_hoi_thao": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "hang_ve": "vip",
    "ghi_chu": "một anh mắt kém cần ngồi bàn đầu gần màn hình chiếu"
  }
]
```

**Link trò chuyện:** https://share.gemini.google/PLDxvUlvtXnG

## 4.3. Báo giá vé hội thảo bằng Chain-of-Thought

**KET QUA AI**

```text
Dưới đây là bảng tính chi tiết từng bước theo đúng thứ tự ưu tiên từ yêu cầu báo giá của nhóm:

### 1. Tiền người lớn

* **Gói đăng ký:** DT (Gói Đầu Tư) — **1.500.000 đồng/người lớn**.
* **Số lượng:** 4 người lớn.
* **Tiền người lớn:** `4 × 1.500.000 = 6.000.000 đồng`.

### 2. Tiền trẻ em

* **Trẻ em từ 6 đến 12 tuổi (tính 50% giá người lớn):** Giá vé mỗi bé là `50% × 1.500.000 = 750.000 đồng`. Nhóm có 2 bé (8 tuổi và 11 tuổi) thuộc diện này: `2 × 750.000 = 1.500.000 đồng`.
* **Trẻ dưới 6 tuổi (miễn phí):** Bé 4 tuổi miễn phí (`0 đồng`).
* **Tiền trẻ em:** `1.500.000 + 0 = 1.500.000 đồng`.

### 3. Tiền vé

* **Tiền vé (trước giảm giá):** `6.000.000 + 1.500.000 = 7.500.000 đồng`.

### 4. Giảm giá nhóm

* **Điều kiện áp dụng:** Nhóm có 4 người lớn (đủ điều kiện từ 4 người lớn trở lên) nên được giảm **10%** trên tổng tiền vé.
* **Số tiền được giảm:** `10% × 7.500.000 = 750.000 đồng`.
* **Tiền vé sau giảm:** `7.500.000 - 750.000 = 6.750.000 đồng`.

### 5. Phụ thu sổ tay

* **Đơn giá:** 200.000 đồng/bộ (không áp dụng giảm giá).
* **Số lượng:** 2 bộ sổ tay lập kế hoạch tài chính cá nhân.
* **Phụ thu sổ tay:** `2 × 200.000 = 400.000 đồng`.

### 6. Tổng tiền

* **Tổng tiền:** `6.750.000 + 400.000 = 7.150.000 đồng`.

[RESULT: 7.150.000 đồng]
```

**Link trò chuyện:** https://share.gemini.google/3cIjXus2J2E6

### b) Kiểm tra kết quả AI

AI làm đúng 

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
```json
{
  "loai_su_co": "sai_khu_vuc",
  "so_khach": 2,
  "so_hiep_bi_anh_huong": 2,
  "tom_tat": "Khách mua gói DT bị xếp ngồi dãy ghế phụ thiếu bàn viết trong 2 phiên học đầu."
}

```
```

**Link trò chuyện:** https://share.gemini.google/q1Lomhy4kKIk

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin (50%)** | 0,0 / 5,0 | Không có dữ liệu thông tin chuẩn của ban tổ chức về giá vé và chính sách hủy vé để đối chiếu trực tiếp, tuy nhiên nội dung đưa ra cam kết mức giá 1.200.000đ/người và hoàn 100% tiền vé khi báo hủy trước 4 ngày mà không có căn cứ đối chứng rõ ràng, đồng thời thiếu cơ sở xác nhận tính chính xác. | Đối chiếu trực tiếp với bảng giá và quy định hủy vé chính thức của ban tổ chức trước khi phản hồi khách hàng; nêu rõ giá niêm yết và điều kiện hoàn/hủy cụ thể theo quy định hiện hành. |
| **Đầy đủ (30%)** | 0,0 / 3,0 | Toàn bộ câu trả lời chỉ gồm: *"Dạ chào anh/chị nha! Vé gói Đầu Tư bên em giá chỉ 1.200.000đ/người thôi, đi học về đầu tư chứng khoán lời khủng luôn ạ. Anh/chị báo huỷ trước 4 ngày thì bên em hoàn lại đủ 100% tiền vé nha, cứ yên tâm chốt đơn đi ạ!"* — không thể hiện việc trả lời đủ hai câu hỏi của khách hàng và hoàn toàn không có lời mời cung cấp ngày hội thảo, số lượng vé muốn đăng ký. | Trả lời đầy đủ từng câu hỏi của khách hàng, đồng thời thêm lời mời cụ thể: *"Anh/Chị vui lòng cho biết ngày hội thảo dự kiến tham dự và số lượng vé cần đăng ký để em hỗ trợ giữ chỗ chính xác ạ."* |
| **Giọng điệu (20%)** | 0,0 / 2,0 | 1. *"Dạ chào anh/chị nha!"* và *"...hoàn lại đủ 100% tiền vé nha, cứ yên tâm chốt đơn đi ạ!"* — dùng trợ từ suồng sã (*"nha"*) và cách thúc ép chốt đơn thiếu chuyên nghiệp. |  |



2. *"...đi học về đầu tư chứng khoán lời khủng luôn ạ."* — hứa hẹn lợi nhuận quá đà, vi phạm chuẩn mực tư vấn tài chính/đầu tư. | *"Kính chào Anh/Chị. Vé gói Đầu Tư hiện có mức giá 1.200.000đ/người. Chương trình trang bị kiến thức và phương pháp nền tảng về đầu tư chứng khoán; kết quả đầu tư thực tế phụ thuộc vào chiến lược và kỷ luật của từng học viên. Theo chính sách hiện hành, yêu cầu hủy vé gửi trước 4 ngày sẽ được hoàn 100% giá trị vé."* |
| **Tổng điểm** | **0,0 / 10,0** | — | — |
```

**Link trò chuyện:** https://share.gemini.google/YAjqcmCxOHSP
