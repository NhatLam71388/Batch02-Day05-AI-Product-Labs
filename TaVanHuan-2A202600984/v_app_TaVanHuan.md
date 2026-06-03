
# BÁO CÁO PHÂN TÍCH SẢN PHẨM AI THỰC TẾ – V-APP AI (V-AI)

**Họ tên:** Tạ Văn Huấn 
**MSSV:** 2A202600984


> **Workshop cá nhân:** Mổ sản phẩm AI thật: **App → Flow → Path yếu → Sửa**  
> **Mục tiêu output:** Sketch **As-Is / To-Be** + **01 Product Decision**, không kể bug rời rạc.

---

# 1. Giới thiệu sản phẩm

## 1.1. Thông tin sản phẩm

**Tên sản phẩm:** V-App AI (V-AI)  
**Loại sản phẩm:** Trợ lý AI trong ứng dụng  
**Chức năng chính:**

- Hỗ trợ bằng voice/text
- Trả lời câu hỏi theo ngữ cảnh
- Tìm kiếm thông tin
- Hỗ trợ người dùng trong hệ sinh thái ứng dụng

Theo mô tả workshop, V-AI hoạt động như một trợ lý AI có khả năng hỗ trợ người dùng trực tiếp trong app.

---

# 2. Promise của sản phẩm (Kỳ vọng của AI)

Trước khi test, cần đọc “promise” của sản phẩm.

### Kỳ vọng sản phẩm mang lại

V-App AI hứa hẹn:

- Trả lời nhanh chóng
- Hiểu câu hỏi tự nhiên
- Đưa thông tin đúng ngữ cảnh
- Hỗ trợ người dùng thuận tiện trong app

### Kỳ vọng người dùng

Người dùng mong muốn:

> “Hỏi nhanh – hiểu đúng – trả lời dễ hiểu”

Đặc biệt trên điện thoại, người dùng thường muốn:

- Câu trả lời ngắn
- Dễ đọc
- Không phải cuộn nhiều

---

# 3. Dùng thử thực tế (2–3 Query thật)

Theo yêu cầu workshop: **thử 2–3 query thật và chụp điểm gãy (kỳ vọng vs thực tế).**

## Query 1: Hỏi thời tiết tại VinUni

### Input

> “Tôi muốn biết thời tiết hiện tại ở Đại học VinUni”

### Kỳ vọng

Người dùng mong đợi:

- Hiển thị thời tiết hiện tại
- Trả lời nhanh
- Ngắn gọn

Ví dụ mong muốn:

> VinUni hiện tại 33°C, trời nhiều mây nhẹ, khả năng mưa thấp.

### Kết quả thực tế

AI:

- Đọc nhiều nguồn
- Tổng hợp dữ liệu
- Trả kết quả rất dài

Bao gồm:

- Nhiệt độ
- Độ ẩm
- Gió
- UV
- Dự báo
- Giải thích mở rộng

### Điểm gãy (Expectation vs Reality)

**Kỳ vọng:** nhanh, ngắn gọn  
**Thực tế:** quá dài, phải đọc nhiều

### Đánh giá

| Tiêu chí | Đánh giá |
|---|---:|
| Đúng nội dung | 9/10 |
| Dễ đọc | 5/10 |
| Trải nghiệm mobile | 5/10 |
| Tốc độ cảm nhận | 6/10 |

---

## Query 2: Hỏi địa điểm VinUni

### Input

> “Đại học VinUni ở đâu?”

### Kỳ vọng

- Có địa chỉ
- Có bản đồ hoặc link nhanh

### Kết quả thực tế

AI có thể trả lời đúng vị trí nhưng thường thiên về text.

### Điểm gãy

Thiếu hành động nhanh (**Quick Action**) như:

- Mở Google Maps
- Chỉ đường

### Nhận xét

AI trả lời đúng nhưng UX chưa tối ưu cho thao tác tiếp theo.

---

## Query 3: Hỏi đề xuất hoạt động

### Input

> “Hôm nay thời tiết ở VinUni có phù hợp đi bộ ngoài trời không?”

### Kỳ vọng

Người dùng muốn:

> “Có/Không + lý do ngắn”

### Thực tế

AI thường đưa nhiều thông tin kỹ thuật.

### Điểm gãy

Người dùng muốn **decision-based answer** nhưng AI lại trả lời kiểu báo cáo.

---

# 4. Vẽ Flow hiện tại (AS–IS)

Theo workshop: đánh dấu **happy / low-confidence / failure / correction**

## Flow hiện tại

```text
User nhập câu hỏi
        ↓
AI bắt đầu tìm kiếm
        ↓
Hiển thị "Đang đọc 6 nguồn"
        ↓
User không biết mất bao lâu
(LOW-CONFIDENCE)
        ↓
AI tổng hợp nhiều thông tin
        ↓
Trả câu trả lời dài
        ↓
User phải đọc nhiều
        ↓
Có thể bỏ sót ý chính
(FAILURE NHẸ)
```

## Phân loại trạng thái

### 1. Happy Path

- AI hiểu đúng câu hỏi
- Có câu trả lời đúng chủ đề

### 2. Low-confidence

Xuất hiện khi:

- “Đang đọc 6 nguồn”
- Không rõ AI đang làm gì
- Không biết mất bao lâu

Người dùng bắt đầu:

> “Ủa có bị lỗi không?”

### 3. Failure

Failure nhẹ xảy ra ở:

> Kết quả quá dài

Người dùng:

- Không đọc hết
- Bỏ qua thông tin quan trọng
- Mất kiên nhẫn

### 4. Correction

Hiện tại correction gần như chưa tốt.

Người dùng phải:

- Tự hỏi lại
- Tự rút gọn câu hỏi

Ví dụ:

> “Tóm tắt ngắn thôi”

---

# 5. Path yếu nhất được chọn

Theo yêu cầu workshop:

> **Chỉ sửa 1 path yếu nhất**

## Path yếu được chọn

### “Kết quả trả về quá dài, khó đọc trên mobile”

Đây là điểm ảnh hưởng UX mạnh nhất.

## Vì sao chọn path này?

Không phải vì AI sai.

Mà vì:

> **AI đúng nhưng trải nghiệm chưa tốt**

User thường cần:

> Đọc nhanh → hiểu nhanh → hành động nhanh

Nhưng flow hiện tại:

> Đọc nhiều → kéo màn hình → lọc thông tin

---

# 6. Phân tích nguyên nhân gốc (Root Cause)

### Nguyên nhân 1: Ưu tiên đầy đủ hơn ngắn gọn

AI cố trả lời quá chi tiết.

### Nguyên nhân 2: Thiếu phân tầng thông tin

Không có:

- Summary trước
- Detail sau

### Nguyên nhân 3: Không tối ưu mobile UX

Text dài gây:

- Khó scan
- Khó đọc
- Khó lấy insight nhanh

---

# 7. Đề xuất TO–BE FLOW (Sửa path yếu nhất)

## Flow mới đề xuất

```text
User nhập câu hỏi
        ↓
AI xác nhận ý định
"Đang lấy thời tiết tại VinUni..."
        ↓
Hiển thị loading rõ ràng
+ thời gian dự kiến
        ↓
AI trả lời bản tóm tắt
        ↓
User đọc nhanh
(HAPPY PATH)
        ↓
Nhấn "Xem chi tiết"
nếu cần
```

## Thiết kế trả lời mới

### Màn hình đầu tiên

🌤 **Thời tiết tại VinUni**

- Nhiệt độ: 33°C
- Cảm giác thực: 40°C
- Khả năng mưa: thấp

**Tóm tắt:**  
Hôm nay trời khá nóng, phù hợp di chuyển ngắn nhưng nên tránh nắng giữa trưa.

### Nút hành động

- Xem chi tiết
- Theo giờ
- Dự báo hôm nay
- Mở bản đồ

---

# 8. Product Decision

## Quyết định sản phẩm

> **Ưu tiên sửa UI/UX hiển thị kết quả trước khi sửa model AI**

## Lý do

AI hiện tại:

✅ Hiểu đúng câu hỏi  
✅ Có dữ liệu  
✅ Tổng hợp được thông tin

Nhưng:

❌ Trình bày chưa tối ưu

Tức là:

> Vấn đề nằm ở UX nhiều hơn AI capability.

## Hành động ưu tiên

### P1 – Quick Summary

Thêm chế độ:

> “Tóm tắt trong 5 giây”

### P2 – Expand/Collapse

Thu gọn/mở rộng kết quả.

### P3 – Action Buttons

Cho phép:

- Chỉ đường
- Xem thời tiết theo giờ
- Refresh

### P4 – Correction Support

Nếu câu hỏi dài:

AI hỏi lại:

> “Bạn muốn bản tóm tắt nhanh hay chi tiết?”

---

# 9. So sánh As-Is và To-Be

| Tiêu chí | As-Is | To-Be |
|---|---|---|
| Độ dài câu trả lời | Dài | Ngắn trước |
| Dễ đọc mobile | Thấp | Cao |
| Hiểu nhanh | Trung bình | Tốt |
| User confidence | Trung bình | Cao |
| Trải nghiệm tổng thể | 6/10 | 8.5/10 |

---

# 10. Kết luận

Sau khi thử nghiệm thực tế V-App AI với nhiều query, có thể thấy sản phẩm đã có nền tảng AI khá tốt về mặt xử lý ngôn ngữ và tổng hợp dữ liệu.

Tuy nhiên, điểm yếu lớn nhất không nằm ở việc trả lời sai mà nằm ở **cách trình bày kết quả**.

Path yếu nhất được chọn là:

> **“AI trả lời quá dài khiến người dùng khó đọc trên điện thoại.”**

Giải pháp đề xuất là chuyển từ:

> **Long Answer First**

sang

> **Quick Summary First**

để tăng trải nghiệm thực tế, giảm cognitive load và giúp người dùng nhận được giá trị nhanh hơn.
