# Hướng dẫn người gửi PR

[English](../../en/review/author.md)

Mục tiêu: reviewer hiểu và quyết định được trong một lần ngồi.

## Trước khi mở PR

1. Tự review diff như người ngoài cuộc. Xóa debug, file rác, commented-out code.
2. Chạy test/lint local của repo đó.
3. **Test cho hành vi mới đi cùng PR này.** “Test để PR sau” không phải PR. PR chỉ-test thì được. PR nền test cái nó giới thiệu (type, schema, stub), không test consumer chưa tồn tại.
4. Description viết xong *trước khi* tag reviewer ([template](../../templates/PULL_REQUEST_TEMPLATE.md)).
5. Nếu PR > ~400 dòng net (không tính lockfile, gen code, xóa nguyên file) — tách. Reviewer được trả lại chỉ vì quá lớn.

“Đủ nhỏ” = **một ý**, review trong 15–25 phút. ~100 dòng thường ổn; ~1000 dòng thường không. Số file cũng tính: 200 dòng / 1 file khác 200 dòng / 40 file.

Số dòng là heuristic cho mọi ngôn ngữ. File generate (protobuf, lockfile, snapshot) không ăn chung ngân sách với logic viết tay.

## Description phải trả lời

- **Làm gì** (1–3 câu).
- **Vì sao** (bug, constraint, link issue).
- **Không làm gì** (phạm vi cố ý bỏ).
- **Cách kiểm tra** (lệnh, case, ảnh nếu UI).
- **Rủi ro / rollback**.

### Dòng đầu

Dòng đầu phải đứng một mình trong `git log`. Viết như hành động change làm, không phải nhãn giai đoạn. Body có thể thêm Why; xóa body thì dòng đầu vẫn hiểu được.

| Tránh | Nên |
|-------|-----|
| Fix bug | Reject revoked refresh tokens after logout |
| Update | Read timeout from config instead of a constant |
| Phase 1 / WIP | Add `BlobStore` trait; caller lands in the next PR |
| as discussed | Delete the unused `parse_header` export |

“Fix bug”, “Update”, “Phase 1”, “WIP”, “as discussed” không phải description.

## Reviewer

Chọn người *hiểu vùng code đó*, không phải “ai đang online”.  
Một reviewer chính là đủ cho PR thường. Tag thêm người thứ hai khi đụng API công cộng, bảo mật, tiền, hoặc data migration.

Solo: [solo.md](../solo.md).

## Khi nhận comment

Đọc [xử lý comment](handling-comments.md). Tóm tắt: sửa code; đừng thắng thread.

## Không

- Trộn formatter toàn repo với feature.
- “Tiện thể” sửa chỗ không liên quan.
- Ép approve vì deadline tự đặt. Deadline cứng: [emergencies.md](../emergencies.md).
- Để nhánh mặc định không build được giữa các PR chồng. Xem [git.md](../git.md#do-not-break-the-build-between-stacked-prs).
