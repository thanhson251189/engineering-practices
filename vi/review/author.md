# Hướng dẫn người gửi PR

[English](../../en/review/author.md)

Mục tiêu: reviewer hiểu và quyết định được trong một lần ngồi.

## Trước khi mở PR

1. Tự review diff như người ngoài cuộc. Xóa debug, file rác, commented-out code.
2. Chạy test/lint local của repo đó.
3. Description viết xong *trước khi* tag reviewer ([template](../../templates/PULL_REQUEST_TEMPLATE.md)).
4. Nếu PR > ~400 dòng net (không tính lockfile, gen code, xóa nguyên file) — tách. Reviewer được trả lại chỉ vì quá lớn.

“Đủ nhỏ” = **một ý**, review trong 15–25 phút. ~100 dòng thường ổn; ~1000 dòng thường không. Số file cũng tính: 200 dòng / 1 file khác 200 dòng / 40 file.

Số dòng là heuristic cho mọi ngôn ngữ. File generate (protobuf, lockfile, snapshot) không ăn chung ngân sách với logic viết tay.

## Description phải trả lời

- **Làm gì** (1–3 câu; dòng đầu = tóm tắt).
- **Vì sao** (bug, constraint, link issue). Không viết “update code”.
- **Không làm gì** (phạm vi cố ý bỏ).
- **Cách kiểm tra** (lệnh, case, ảnh nếu UI).
- **Rủi ro / rollback**.

## Reviewer

Chọn người *hiểu vùng code đó*, không phải “ai đang online”.  
Một reviewer chính là đủ cho PR thường. Tag thêm người thứ hai khi đụng API công cộng, bảo mật, tiền, hoặc data migration.

## Khi nhận comment

- Sửa hoặc giải thích. Không ignore im lặng.
- Không bắt buộc làm hết Nit.
- Cùng một điểm tranh 2 vòng → gọi 10–15 phút, ghi kết luận lên PR, rồi đi tiếp.
- Push tiếp thì reply “done” ở comment đã xử lý để reviewer không phải đoán.

## Không

- Trộn formatter toàn repo với feature.
- “Tiện thể” sửa chỗ không liên quan.
- Ép approve vì deadline tự đặt. Deadline cứng: [emergencies.md](../emergencies.md).
