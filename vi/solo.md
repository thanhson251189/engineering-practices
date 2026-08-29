# Solo / một người

[English](../en/solo.md)

“Cần 1 approve”, “chọn người own vùng code”, “phản hồi trong một ngày làm việc” giả định có người thứ hai. Không chạy nguyên văn trên repo một người, vẫn push thẳng nhánh mặc định.

Phần còn lại của guide vẫn áp: change nhỏ, sàn vs chuẩn approve, test, docs, không tách giả. Agent theo [AGENTS.md](../AGENTS.md) và [bản Việt](AGENTS.md).

## Thay reviewer thứ hai bằng gì

1. **Tự review** theo [checklist author](review/author.md) trước khi merge. Đọc diff như người lạ. Cùng giới hạn size.
2. **Agent được review.** Đó là thêm một cặp mắt, không phải LGTM. Chỉ tính sau khi change đã qua cổng size, test bắt buộc, và docs/hợp đồng. Đừng coi “model bảo LGTM” là approve.
3. Nên mở PR dù tự merge. Description là hồ sơ. Push thẳng nhánh mặc định được với chore/fix nhỏ; không phải mặc định cho đổi hành vi.

## Không

- Bịa người approve thứ hai (kể cả agent) để thỏa checkbox branch protection mà repo không có.
- Bỏ test vì không ai nhìn.
- Stack API nền rồi không bao giờ land consumer.

Khi có người thứ hai: chuyển sang rule team trong [principles.md](principles.md) và [adopting.md](adopting.md), không cần viết lại trang này.
