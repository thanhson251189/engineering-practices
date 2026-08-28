# Emergency

[English](../en/emergencies.md)

Đi tắt review **chỉ** khi chậm hơn sẽ gây thiệt hại thật sự.

## Là emergency

- Lỗ bảo mật đang lộ hoặc exploit được.
- Production đang đau rõ (lỗi rộng, mất dữ liệu, tiền sai).
- Nghĩa vụ pháp lý / hợp đồng có deadline cứng — miss thì hậu quả nặng.
- Rollback để dừng cháy.

## Không phải emergency

- Muốn ra tuần này thay vì tuần sau.
- Làm feature lâu rồi, muốn merge cho xong.
- Reviewer đang nghỉ / chậm.
- Demo nội bộ.
- Build đỏ do PR của mình — sửa theo quy trình thường.

## Cách đi tắt

1. PR vẫn nhỏ nhất có thể.
2. Description bắt đầu bằng `EMERGENCY:` + lý do.
3. Một người hiểu vùng code đó vẫn phải nhìn diff (pair cũng tính là đã review).
4. Follow-up PR trong **một ngày làm việc** nếu đã bỏ test/docs/cleanup.
5. Sau đó: 5–10 dòng postmortem (chuyện gì, vì sao đi tắt, lần sau tránh).

Hotfix không được thành lối đi thường.
