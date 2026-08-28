# Git và kích thước thay đổi

[English](../en/git.md)

## Nhánh

- Nhánh mặc định luôn ship được.
- Branch sống ngắn (vài ngày). Prefix gợi ý: `feat/`, `fix/`, `refactor/`, `chore/`, `hotfix/`.
- Một branch ≈ một PR ≈ một ý.

## Commit

Conventional Commits là tùy chọn, không phụ thuộc ngôn ngữ:

```
feat(auth): reject revoked refresh tokens
fix(api): do not return 500 when field X is missing
```

Dòng đầu là câu hoàn chỉnh, viết cho `git log`.  
Squash khi merge nếu history nhánh bẩn — chọn một lần cho cả team, ghi vào đây.

## PR quá lớn

Reviewer được reject chỉ vì size.

Cách tách (mọi ngôn ngữ):

- **Xếp chồng:** PR nền (types, stub, schema) → PR dùng.
- **Theo lớp:** contract trước, implementation sau.
- **Theo lát dọc:** một use-case xuyên stack, rồi use-case kế.
- Refactor trước để feature PR mỏng.

Không tách giả: 5 PR không merge độc lập được, build gãy giữa chuỗi.

## Không phá build giữa các PR chồng

Mỗi PR trong stack phải merge được vào nhánh mặc định một mình: test bắt buộc xanh, tree compile, không schema dở.

PR sau được phụ thuộc PR này. PR này không được phụ thuộc PR sau mới build được.

CI đỏ đến khi “phần còn lại của stack land” thì đó là một PR giả dạng stack. Merge một cục hoặc cắt nền mỏng hơn.

## Stacked PR và API chưa dùng

Nguyên tắc 5 cấm để API public không caller như **trạng thái kết thúc** của việc. Không cấm PR nền.

API mới (hoặc stub, type, trait, hàm export) được land khi chưa có caller trong repo nếu **đủ** các điều:

1. Description ghi PR tiếp theo sẽ gọi nó (link hoặc tiêu đề).
2. CI bắt buộc được chỉnh để cảnh báo unused / dead-code không fail **PR nền này**. Cách làm tùy ngôn ngữ (thu hẹp visibility, allow-list cho package đó, chưa export cho đến khi có consumer). Không nới check trên nhánh mặc định vĩnh viễn.
3. PR consumer land trước khi API bị coi là hợp đồng ổn định.

Nếu consumer bị bỏ: revert hoặc xóa API chết ở change kế. Không để nằm.

## File máy sinh

Lockfile, codegen, snapshot: ghi rõ trong description. Reviewer không cần đọc từng dòng generated nếu tool tin cậy; vẫn phải hiểu *vì sao* generate lại.
