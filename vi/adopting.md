# Đưa rule vào repo sản phẩm

[English](../en/adopting.md)

Repo practices chỉ có giá trị khi **gắn vào chỗ người ta mở PR**. Chưa có template PR và check bắt buộc thì các trang này là markdown không ai đọc.

Không phụ thuộc stack.

Một người? Làm template + CI + link trước. Bỏ “1 approve” đến khi có người thứ hai. Xem [solo.md](solo.md).

## Tối thiểu, một buổi

1. Copy `templates/PULL_REQUEST_TEMPLATE.md` → repo sản phẩm `.github/PULL_REQUEST_TEMPLATE.md`.
2. Nếu từ hai người: PR vào nhánh mặc định cần 1 approve.
3. CI bắt buộc phải xanh (test + lint/format).
4. Link repo practices này vào README sản phẩm và template PR. Doc/skill của agent trỏ **repo này**, không trỏ bản Google đã archive.
5. Bật formatter + linter, auto-format. Xóa debate indent khỏi review.
6. Nếu đã rõ owner, copy `templates/CODEOWNERS.example`.

## Việc không làm tuần đầu

- 20 file style theo từng ngôn ngữ lập trình.
- Conventional Commits + squash + rebase + signed commit cùng lúc.
- Coverage 90%.
- 2 reviewer cho mọi PR.

Thêm rule khi một class lỗi lặp lại ≥ 2 lần. Không thêm vì “Google có”.

## Review chính repo practices

Đổi rule bằng PR. Dòng đầu description: vì sao rule cũ thất bại.  
Sửa **en/** và **vi/** trong cùng một PR.  
Rule không dùng trong 60 ngày → xóa hoặc hạ thành Nit.
