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

## File máy sinh

Lockfile, codegen, snapshot: ghi rõ trong description. Reviewer không cần đọc từng dòng generated nếu tool tin cậy; vẫn phải hiểu *vì sao* generate lại.
