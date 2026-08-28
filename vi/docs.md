# Docs

[English](../en/docs.md)

Viết docs khi **hợp đồng** đổi, không khi cảm thấy có tội.

## Phải cập nhật khi

- Hành vi user-facing đổi.
- API / event / schema public đổi.
- Cách chạy, env, feature flag, runbook deploy/rollback đổi.
- Quyết định design có tuổi thọ > 1 sprint → ADR ngắn (context, decision, consequences).

## Không cần

- Comment từng dòng giải thích *what* mà tên đã nói.
- README dài kể lịch sử team.
- Docs cho abstraction “phòng khi”.

## Chỗ sống

- Hướng dẫn chạy/dev: README repo sản phẩm.
- Hợp đồng API: ngay cạnh code hoặc spec repo đang dùng.
- Quyết định bền: `/docs/adr/` trong repo sản phẩm.
- Quy trình review: **repo này**.
