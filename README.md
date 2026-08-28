# Engineering Practices

[English](#english) · [Tiếng Việt](#tiếng-việt)

Language-agnostic working agreement for any stack. Not a style guide.

---

## English

**Floor:** a merge must not make codebase health worse (except a defined [emergency](en/emergencies.md)).  
**Approval bar:** approve when the change **improves** health, even if it is not perfect.  
Every change must also be **small enough to review in one sitting**.

### Start here

| Role | Page |
|------|------|
| Everyone | [Principles](en/principles.md) |
| Solo / one human | [Solo](en/solo.md) |
| PR author | [Author guide](en/review/author.md) |
| Reviewer | [Reviewer guide](en/review/reviewer.md) |
| How to write comments | [Comments](en/review/comments.md) |
| Branches, size, stacking | [Git](en/git.md) |
| Tests | [Testing](en/testing.md) |
| When to write docs | [Docs](en/docs.md) |
| Shortcuts | [Emergencies](en/emergencies.md) |
| Wire into a product repo | [Adopting](en/adopting.md) |

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

**Sàn:** merge không được làm codebase health tệ hơn (trừ [emergency](vi/emergencies.md) đã định nghĩa).  
**Chuẩn approve:** approve khi change **cải thiện** health, dù chưa hoàn hảo.  
Mọi thay đổi còn phải **đủ nhỏ để review trong một lần ngồi**.

### Bắt đầu từ đây

| Vai trò | Trang |
|---------|-------|
| Mọi người | [Nguyên tắc](vi/principles.md) |
| Solo / một người | [Solo](vi/solo.md) |
| Người gửi PR | [Hướng dẫn author](vi/review/author.md) |
| Reviewer | [Hướng dẫn reviewer](vi/review/reviewer.md) |
| Cách viết comment | [Comment](vi/review/comments.md) |
| Nhánh, size, stack PR | [Git](vi/git.md) |
| Test | [Test](vi/testing.md) |
| Khi nào viết docs | [Docs](vi/docs.md) |
| Đi tắt | [Emergency](vi/emergencies.md) |
| Gắn vào repo sản phẩm | [Adopting](vi/adopting.md) |

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
en/          English
vi/          Tiếng Việt
templates/   PR template (bilingual) + CODEOWNERS example
```

`en/` and `vi/` are the same rules. Change both in one PR. If they drift, **English is the source of truth** until the Vietnamese page is updated.

## Inspiration

- [Google Engineering Practices](https://google.github.io/eng-practices/) — review mechanics (CC BY 3.0). This repo is not a copy of that text.
- *Software Engineering at Google* — code that lives for years

Take the reasons. Do not copy Google's org chart.
