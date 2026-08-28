# Xử lý comment review

[English](../../en/review/handling-comments.md)

Trang này cho **author khi nhận comment**. Cách reviewer viết: [comments.md](comments.md).

## Phản hồi mặc định

Sửa code. Comment trên tool là bước cuối, sau khi diff đã rõ hơn.

Reviewer không hiểu change thì code hoặc description chưa đủ rõ. “Đã giải thích trong reply” không phải cách sửa.

## Làm

- Trả lời mọi comment chặn merge: đã xong, hoặc vì sao không, kèm commit mới.
- Nhận Nit khi rẻ. Bỏ Nit khi nó chống lại ý của PR; nói một lần.
- Cùng một điểm sau 2 vòng: nói 10–15 phút, ghi quyết định lên PR, merge hoặc tách. Đừng để PR nằm im.
- Coi comment là về change, không phải về người.

## Không

- Trả lời câu hỏi design chỉ bằng chữ, để nguyên code.
- Cãi sở thích mà formatter không bắt. Ở đó preference của author thắng ([nguyên tắc](../principles.md) §2).
- Chờ vài ngày cho câu reply hoàn hảo. Push bản sửa trước.
- Coi “LGTM” của agent là comment người đã xong ([solo.md](../solo.md)).
