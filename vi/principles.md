# Nguyên tắc

[English](../en/principles.md)

Ưu tiên từ trên xuống: rule dưới không được phá rule trên.

Áp dụng cho mọi ngôn ngữ và runtime. Gợi ý chỉ đúng với một ngôn ngữ lập trình thì không thuộc bộ này.

Repo chỉ một người? Đọc [solo.md](solo.md). SLA và “chọn owner” ở nguyên tắc 4 không áp nguyên văn.

## 1. Code health tăng theo thời gian

**Sàn:** change không được làm code health tệ hơn.  
**Chuẩn approve:** reviewer **nên approve** khi PR chắc chắn cải thiện health — dễ hiểu hơn, dễ sửa hơn, hoặc ít rủi ro hơn hôm qua — **dù chưa hoàn hảo**.

“Không làm xấu đi” không phải mục tiêu. Đó chỉ là đường không được vượt.  
Không tồn tại PR hoàn hảo. Tìm cải thiện liên tục.  
Không merge thứ làm codebase tệ hơn — trừ [emergency](emergencies.md).

## 2. Facts thắng preference

- Tranh luận bằng hành vi, rủi ro, dữ liệu, nguyên tắc thiết kế.
- Việc thuần túy “trông đẹp hơn” mà formatter/linter không bắt → preference của author thắng, trừ khi phá consistency đang có trong file đó.
- Design gần như không bao giờ là preference. Nếu có vài cách đều đúng, author chọn. Reviewer không bắt đổi vì “tôi hay viết kiểu kia”.

## 3. Một PR = một ý

PR phải tự chứa: reviewer hiểu *vì sao* và *ảnh hưởng gì* mà không cần đọc 4 PR khác (trừ chuỗi đã ghi rõ trong description).

Tách:

- refactor khỏi feature / bugfix
- schema / API contract khỏi consumer nếu merge độc lập được
- config / flag khỏi implementation khi rollback cần độc lập

Stack PR nền: xem [git.md](git.md#stacked-prs-and-unused-apis).

## 4. Tốc độ team hơn tốc độ cá nhân

Áp dụng khi có hơn một người review. Solo: [solo.md](solo.md).

Review chậm làm cả team chậm, khuyến khích “merge cho xong”, giết cleanup.

- Phản hồi review đầu trong **một ngày làm việc** (chưa cần approve xong).
- Đừng ngắt đoạn đang flow coding chỉ để review; review ở breakpoint.
- Có thể **Approve** kèm comment nhỏ nếu tin author sẽ xử lý, hoặc comment chỉ là Nit.

## 5. Nhánh chính luôn ship được

Mỗi merge:

- không làm đỏ bộ test bắt buộc
- không để API/cờ chết không dùng **như trạng thái kết thúc của việc đang làm**
- rollback được bằng revert hoặc flag

PR nền được phép land API chưa có caller trong repo. Đó không phải API chết nếu description ghi PR tiếp theo và CI được chỉnh để cảnh báo unused không fail *PR đó*. Chi tiết: [git.md](git.md#stacked-prs-and-unused-apis).

## 6. Viết cho người sửa sau 6 tháng

Tên rõ. Comment giải thích *why*. Docs cập nhật khi hành vi user-facing hoặc hợp đồng API đổi.  
Đừng implement “phòng khi cần sau này”.
