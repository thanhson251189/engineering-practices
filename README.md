# Engineering Practices

[English](#english) · [Tiếng Việt](#tiếng-việt)

Language-agnostic working agreement for any stack. Not a style guide.

---

## English

Each change merged to the default branch must **improve (or at least not worsen) codebase health**, and must be **small enough to review in one sitting**.

| Role | Start here |
|------|------------|
| Everyone | [en/principles.md](en/principles.md) |
| PR author | [en/review/author.md](en/review/author.md) |
| Reviewer | [en/review/reviewer.md](en/review/reviewer.md) |
| Adopt in a product repo | [en/adopting.md](en/adopting.md) |

If a rule fights a deadline, **principles win**. If you still disagree: 15-minute talk, write the decision on the PR, merge or split. Do not leave the PR idle.

### Rule words

| Word | Meaning |
|------|---------|
| **Must** | No valid exception |
| **Must not** | Never, except a defined emergency |
| **Should** | Do it unless the PR explains why not |
| **Avoid** | Don't, unless you have a concrete reason |
| **Nit:** | Polish. Must not block merge |

### Out of scope

- Indent, quotes, import order → formatter/linter
- System architecture → ADR / design doc
- Product/sprint process → elsewhere
- Language-specific idioms → optional add-on later, not here

---

## Tiếng Việt

Mỗi thay đổi merge vào nhánh chính phải **cải thiện (hoặc ít nhất không làm xấu đi) sức khỏe codebase**, và phải **đủ nhỏ để review trong một lần ngồi**.

| Vai trò | Đọc |
|---------|-----|
| Mọi người | [vi/principles.md](vi/principles.md) |
| Người gửi PR | [vi/review/author.md](vi/review/author.md) |
| Reviewer | [vi/review/reviewer.md](vi/review/reviewer.md) |
| Gắn vào repo sản phẩm | [vi/adopting.md](vi/adopting.md) |

Rule xung đột deadline: **principles thắng**. Vẫn bất đồng: nói 15 phút, ghi quyết định lên PR, merge hoặc tách. Đừng để PR nằm im.

### Ngôn ngữ rule

| Từ | Nghĩa |
|----|--------|
| **Phải** | Không có lý do hợp lệ để bỏ |
| **Không** | Không làm, trừ emergency đã định nghĩa |
| **Nên** | Làm trừ khi giải thích được trên PR |
| **Tránh** | Đừng làm nếu chưa có lý do cụ thể |
| **Nit:** | Polish. Không chặn merge |

### Việc không nằm ở đây

- Indent, quote, import order → formatter/linter
- Kiến trúc hệ thống → ADR / design doc
- Quy trình product/sprint → chỗ khác
- Idiom riêng từng ngôn ngữ lập trình → add-on sau, không nhét vào bộ gốc

---

## Layout

```
en/   English
vi/   Tiếng Việt
templates/   shared PR template (bilingual) + CODEOWNERS example
```

`en/` and `vi/` are the same rules. Change both in one PR. If they drift, **English is the source of truth** until the Vietnamese page is updated.

## Inspiration

- [Google Engineering Practices](https://google.github.io/eng-practices/) — review mechanics
- *Software Engineering at Google* — code that lives for years

Take the reasons. Do not copy Google's org chart.
