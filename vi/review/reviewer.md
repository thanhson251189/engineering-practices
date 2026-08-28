# Hướng dẫn reviewer

[English](../../en/review/reviewer.md)

Nhiệm vụ: bảo vệ code health, **không** viết lại PR theo tay mình.

Không phụ thuộc ngôn ngữ lập trình. Đừng bắt idiom của ngôn ngữ bạn thích nếu repo đang viết ngôn ngữ khác.

## Thứ tự nhìn

1. **Design** — đúng chỗ trong hệ thống? Đúng lớp? Nhánh chết / abstraction sớm?
2. **Hành vi** — làm điều author tuyên bố? Tốt cho user của đoạn code đó?
3. **Phức tạp** — đơn giản hơn được không? Người lạ đọc được không?
4. **Test** — có test đúng hành vi mới? Test có dễ vỡ / test implementation detail không?
5. **Tên** — đọc tên biết việc.
6. **Comment / docs** — why, không phải what. API/user-facing đã cập nhật chưa?
7. **Style** — để máy bắt. Chỉ comment style khi linter sót hoặc phá consistency file đang sửa.

Đọc **mọi dòng** được assign. Nhìn context file, không chỉ hunk xanh đỏ.

## Chuẩn approve

Approve khi PR **cải thiện code health**, không khi hết chỗ chê.

Prefix `Nit:` cho polish.  
Prefix `Blocking:` khi không merge được nếu chưa xử lý (dùng tiết kiệm).

Khen chỗ làm đúng — review cũng là mentoring.

## Tốc độ

- Không đang flow → review sớm.
- Phản hồi đầu trong một ngày làm việc.
- Quá lớn → yêu cầu tách, đừng “review cho có”.
- Khác timezone: cố comment trước khi author bắt đầu ngày làm việc của họ.

Approve kèm comment khi:

- tin author xử lý nốt, hoặc
- comment không bắt buộc, hoặc
- chỉ là sửa nhỏ (import, typo, xóa dep chết).

Ghi rõ ý nào là bắt buộc.

## Không

- Bắt đổi design vì preference.
- Review hộ CI: test/lint bắt buộc đỏ thì bảo author sửa trước khi đi sâu.
- Giữ PR vì “chưa rảnh nói chuyện”. Escalate: author ↔ reviewer → người own module → lead. PR không được treo.
