# Individual Reflection — Tran Van Huy

## Batch
**Mã học viên:** 2A202600712  
**Tên nhóm:** ColorOfDreams  
**Track:** AI Travel / Planning Assistant  

---

## 1. Vai trò trong nhóm

- Phụ trách SPEC (thin SPEC sections 6–7: Four paths & Failure mode)
- Hỗ trợ review evidence pack và synthesis toolkit
- Tham gia self-use ChatGPT/Gemini để tìm điểm gãy trong travel planning workflow

---

## 2. Việc đã làm

| Việc | Chi tiết |
|---|---|
| Self-use | Dùng ChatGPT và Gemini để thử lập lịch trình chuyến đi 3 ngày 2 đêm từ Hưng Yên ra biển. Quan sát điểm AI trả về quá nhiều option, thiếu kiểm chứng, khó chỉnh sửa. |
| Four paths | Viết 4 path (Happy, Low-confidence, Failure, Correction) cho thin SPEC dựa trên evidence từ self-use và tham khảo competitor (Layla, Tripadvisor Trips). |
| Failure mode | Xác định failure mode nguy hiểm nhất: AI trả về quá nhiều thông tin chung chung → user bị quá tải, không chọn được cung, mất niềm tin. Đề xuất mitigation: giới hạn 2–3 option, hỏi làm rõ trước, đánh dấu độ tin cậy. |
| Thin SPEC | Hoàn thiện sections 6 và 7 trong thin-spec-template.md của nhóm. |

---

## 3. Phần AI hỗ trợ

- Sử dụng ChatGPT/Gemini để simulate travel planning workflow và tìm điểm gãy.
- Dùng AI để brainstorm các failure mode có thể xảy ra và mitigation tương ứng.
- AI hỗ trợ tra cứu nhanh thông tin về các điểm đến ven biển miền Bắc và Bắc Trung Bộ (khoảng cách, chi phí, thời gian di chuyển).

---

## 4. Bài học sau demo / workshop

- Một build slice tốt không chỉ là "AI làm gì", mà còn là "AI không làm gì" và "khi AI sai thì sao".
- Bốn paths giúp nhóm hình dung rõ ràng các kịch bản cần test trước khi build, thay vì chỉ code xong rồi mới nghĩ đến failure.
- Failure mode nguy hiểm nhất thường đến từ chính điểm mạnh của AI (trả lời nhanh, nhiều) biến thành điểm yếu (quá tải thông tin, thiếu kiểm chứng).
- Việc có evidence từ self-use trước khi viết SPEC giúp các quyết định trong thin SPEC có căn cứ, không bị "ảo".

---

## 5. Cam kết cho Day 06

- Hỗ trợ team test failure path trong prototype.
- Đảm bảo prototype có cơ chế đánh dấu "cần kiểm chứng" và giới hạn số option khi đề xuất cung đường.
- Sẵn sàng hỗ trợ demo script và repo nếu cần.
