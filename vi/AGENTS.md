# Hợp đồng agent

[English](../AGENTS.md)

File này là thỏa thuận cho **mọi coding agent** trên repo đã nhận bộ practices. Người đọc các trang đầy đủ. Agent phải theo file này trước.

Lệch bản dịch thì **English là nguồn**.

## Đọc trước khi sửa

1. [principles.md](principles.md)
2. [review/author.md](review/author.md)
3. [testing.md](testing.md)
4. [review/handling-comments.md](review/handling-comments.md)
5. Repo một người? [solo.md](solo.md)

Không bịa style guide theo ngôn ngữ. Không lấy `google/eng-practices` (đã archive) thay bộ này.

## Phải

- Một PR một ý. Có ý thứ hai thì tách trước khi sửa tiếp.
- Test hành vi mới nằm **cùng diff**. “Test để PR sau” là chưa xong.
- Description đủ template sản phẩm: Làm gì, Vì sao, ngoài phạm vi, cách test, rủi ro/rollback.
- Dòng đầu đứng một mình trong `git log`. Không `Fix bug`, `Update`, `WIP`, `Phase 1`, `as discussed`.
- Không trộn format toàn repo hoặc refactor lạc đề với feature.
- Không để API public chết như trạng thái kết thúc. PR nền phải ghi PR consumer; không nới CI vĩnh viễn.
- Mỗi PR trong stack tự build và qua check bắt buộc.
- Sửa code, đừng thắng thread review.

## Cấm gọi là xong

- “LGTM” / “looks good” do chính agent viết. Đó không phải approve.
- CI bắt buộc đỏ (test, format, lint) trên repo **sản phẩm**.
- Why trống, hoặc title chỉ là nhãn giai đoạn.
- File ngoài ý của PR.

## Dừng, hỏi người

- Public API, schema, wire format, event contract.
- Secret, credential, dữ liệu prod, migration phá dữ liệu.
- Diff > ~400 dòng viết tay, hoặc nhiều file cho một ý.
- Không giải thích được Why trong hai câu.
- Không biết lệnh CI của repo sản phẩm — không đoán stack rồi “cho chạy được”.

## Xong nghĩa là

1. Check bắt buộc trên repo sản phẩm xanh, hoặc báo đúng lệnh đã fail.
2. Đủ mục template PR.
3. Diff chỉ chứa ý đã nêu.
4. Hành vi mới có test trong diff này, hoặc description nói vì sao không test được và vì sao chấp nhận được.

`AGENTS.md` ở repo sản phẩm được thêm lệnh (test, lint, run). Không được nới file này.
