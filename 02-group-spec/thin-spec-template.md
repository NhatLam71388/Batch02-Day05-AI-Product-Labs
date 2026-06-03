# Template — Thin SPEC Cuối Day 05

Thin SPEC không phải PRD đầy đủ. Đây là bản cam kết đủ rõ để sáng Day 06 nhóm build ngay.

## 1. Track, product/app và user

**Track:**  
**Product/app thật:**  
**User cụ thể:**  
**Nhóm có phải user thật không? Nếu không, khác ở đâu?**  

## 2. Evidence summary

| Evidence | Nguồn | User/pain nói lên điều gì? | SPEC phải đổi gì? |
|---|---|---|---|
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

## 3. Pain statement

```text
User [ai] đang gặp khó ở [bước/workflow],
vì [nguyên nhân hoặc điểm gãy],
dẫn tới [hậu quả].
Bằng chứng chính là [quote/screenshot/review/observation].
```

## 4. Build slice

```text
Cho [user] đang [task/workflow],
prototype sẽ dùng AI để [augment/automate hành động hẹp],
tạo ra [output],
và xử lý [failure mode] bằng [mitigation].
```

## 5. Auto/Aug decision

Chọn một:

- [ ] **Augmentation:** AI gợi ý/draft/phân loại, user quyết cuối.
- [ ] **Conditional automation:** AI tự làm trong case hẹp; case mơ hồ/rủi ro chuyển người.
- [ ] **Automation:** AI tự quyết và tự hành động.

**Lý do chọn:**  
**Human role:** reviewer / decider / trainer / rescuer / none  

## 6. Four paths

| Path | Prototype phải thể hiện gì? |
|---|---|
| Happy | User nhập nhu cầu rõ: xuất phát Hưng Yên/Hà Nội, 3 ngày 2 đêm, ô tô tự lái, muốn biển vắng. AI hỏi thêm vài câu làm rõ → đề xuất 2–3 cung phù hợp → user chọn 1 cung → AI tạo timeline chi tiết từng ngày kèm chi phí, độ mệt, điểm cần kiểm chứng. |
| Low-confidence | AI thiếu dữ liệu chắc chắn về giá phòng, thời tiết, giờ mở cửa, thời gian di chuyển. AI không nói chắc mà đánh dấu rõ "cần kiểm chứng" và gợi ý user check trên Maps/booking app trước khi đi. |
| Failure | User nhập yêu cầu bất khả thi: "3 ngày 2 đêm đi Đà Nẵng bằng xe máy từ Hưng Yên, ngân sách 500k/người, không muốn mệt". AI cảnh báo không khả thi và đề xuất cung gần hơn (Hải Tiến, Cát Bà, Cô Tô, Hải Hòa) kèm lý do vì sao. |
| Correction | Sau khi có lịch trình, user nói "rẻ hơn", "ít chạy xe hơn", "biển vắng hơn", "thêm ăn hải sản" hoặc "đổi sang trời mưa". AI chỉ sửa phần liên quan trong lịch trình, không regenerate toàn bộ từ đầu. |

## 7. Failure mode nguy hiểm nhất

```text
Nếu user nhập ý định mơ hồ hoặc thiếu thông tin,
AI có thể trả về quá nhiều option, thông tin chung chung, thiếu kiểm chứng và không hỏi làm rõ nhu cầu,
hậu quả là user bị quá tải, không chọn được cung phù hợp, mất niềm tin và quay lại tự lên plan thủ công.
Prototype sẽ xử lý bằng giới hạn 2–3 option, đánh dấu rõ độ tin cậy, hỏi làm rõ 3–5 câu trước khi generate và cho phép chỉnh nhanh từng phần.
Owner kiểm thử path này là TranVanHuy.
```

## 8. Owner plan cho sáng Day 06

| Thành viên | Việc phụ trách | Bằng chứng cần có trong repo |
|---|---|---|
|  | Research / evidence |  |
|  | SPEC |  |
|  | Prototype |  |
|  | Test / failure path |  |
|  | Demo script / repo |  |
