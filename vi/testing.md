# Test

[English](../en/testing.md)

Rule dưới đây không gắn framework. Từng repo sản phẩm tự điền lệnh.

## Luật

- PR đổi hành vi **phải** có test cho hành vi mới, hoặc giải thích vì sao không test được và vì sao khoảng trống đó chấp nhận được.
- Refactor thuần: test cũ phải giữ tín hiệu. Thiếu test thì **thêm test trước**, refactor sau — tốt nhất hai PR.
- Test hành vi, không test implementation detail (tên private, số lần gọi mock nội bộ) trừ khi đó *là* hợp đồng.

## “Đủ” là gì

Đủ để:

1. bắt regression của đúng bug/feature này,
2. người sau dám sửa file mà không đoán.

Không tối ưu coverage % trừ khi repo sản phẩm đã chọn ngưỡng và CI đang đo.

## Test xấu

- Flaky.
- Phụ thuộc thời gian tường, network thật, thứ tự test.
- Setup 200 dòng cho 1 assert.
- Copy-paste cùng fixture với 1 field khác.

PR thêm test kiểu này: `Blocking`, hoặc yêu cầu tách. Đừng “lần sau tính”.

## Điền ở repo sản phẩm (không viết trong guide này)

- Lệnh test mặc định
- Layer CI bắt buộc (unit / integration / contract / e2e)
- Được phép mock gì
- Cấm mock gì
