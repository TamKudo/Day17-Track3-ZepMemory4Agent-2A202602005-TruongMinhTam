# README_submission.md

## Phân tích benchmark

**1. Layer hit rate thấp nhất?** Practice student đạt 11/11 (100%). Nhưng so với baseline no-memory, `long_term` là layer rủi ro nhất: cả 4 case (E02, E03, E08, E09) fail hoàn toàn khi thiếu Context Block, vì preference/open-loop/constraint chỉ tồn tại qua nhiều session.

**2. Query nào retrieve nhiều token nhất?** E03 ("open loop/deadline nào chưa xong?") — 1331 retrieved tokens, vì Context Block trả cả `<USER_SUMMARY>` lẫn `<EPISODES>` để giữ được `benchmark report` và `16:00`.

**3. E07 (mixed) cần layer nào?** Long-term + semantic. `budget_breakdown` cho thấy `long_term.raw_tokens=1318` bị trim còn `used_tokens=324`, `semantic.used_tokens=148`. Hai evidence bắt buộc: `Python` (long-term, preference cá nhân) và `Idempotency-Key` (semantic, payment rule).

**4. Token reduction?** Memory-enabled trung bình chỉ 14.2% so với no-memory 81.8% (`comparison.md`). No-memory "giảm" nhiều hơn vì nó gần như không retrieve gì (hit rate 18.2%, chỉ 2/11 pass nhờ short-term local) — reduction cao ở đây là dấu hiệu retrieval rỗng, không phải hiệu quả.

## Reflection bắt buộc

**Layer quan trọng nhất:** `long_term`, chiếm 4/11 case (E02, E03, E08, E09) và là layer duy nhất phải xử lý cả cross-session recall lẫn recency/user-isolation cùng lúc — sai `user_id` hoặc bỏ `prime_eval_thread` sẽ gây leak hoặc mất context ngay.

**Trade-off Context Block (Zep) vs Redis+Qdrant:** Zep tự tổng hợp relevance + recency qua nhiều thread không cần tự thiết kế schema, nhưng phụ thuộc mạng (latency 250ms–2.2s đo được) và ít kiểm soát cách chọn evidence. Redis+Qdrant (`local_baseline`) gần như tức thời, toàn quyền kiểm soát TTL/score, nhưng phải tự xây recency, cross-session linking và provenance từ đầu — không khả thi trong 170 phút.

**Guardrail chống memory poisoning:** Theo `AGENTS.md`, heartbeat/background pass không được tự cấp quyền mới cho mình, và cao-impact preference/task change phải qua review trước khi ghi durable (`heartbeat --dry-run` chỉ đề xuất ACTION, không tự ghi). Mọi durable write giữ `source`, `timestamp`, `confidence`, `validity` (`MEMORY_SCHEMA.md`) để truy vết nguồn gốc.

**E08 recency:** BLUEBIRD-42 là constraint mới theo scope project cụ thể (TypeScript/NestJS), thắng preference chung (Python) của Minh chỉ trong scope đó — đúng conflict rule "recency plus scope" của `MEMORY.md`, không xóa preference cũ ở scope khác.

**E10 compaction:** `REVIEW-DEADLINE-1600`/`Friday`/`16:00` sống sót trong `<DURABLE_NOTES>` dù bị evict khỏi `<RECENT_TURNS>` khi giảm `max_recent_messages` 6→4, vì `extract_durable_notes` bắt marker viết hoa và từ khóa constraint trước khi turn cũ bị bỏ.
