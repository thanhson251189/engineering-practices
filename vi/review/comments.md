# Cách viết comment

[English](../../en/review/comments.md)

Comment để **thay đổi code hoặc chốt quyết định**, không để chứng minh đã đọc diff.

## Hình thức

- Chỉ vào hành vi / rủi ro / nguyên tắc, không vào người.
- Nếu biết hướng sửa, đề xuất cụ thể hoặc sketch. Đừng chỉ “đoạn này chưa ổn”.
- Một comment = một ý. Không tiểu luận.
- Hỏi trước khi kết luận, khi chưa chắc author đã cân nhắc gì:

  > “Có lý do không dùng helper sẵn có ở `foo`?”

## Mẫu

```
Blocking: hàm này nuốt lỗi mạng. Caller không phân biệt timeout và 4xx.
Nên propagate hoặc wrap thành kiểu lỗi hiện có trong package.

Nit: `d` → `delay` cho khớp các hàm cạnh đó.
```

Dùng cùng prefix trong mọi ngôn ngữ của repo sản phẩm.

## Giọng

Lịch sự, thẳng. Tránh mỉa.  
“Chúng ta” thay vì “bạn sai”.  
Không dùng review để dạy cả một chủ đề — link docs; để Nit nếu không chặn merge.
