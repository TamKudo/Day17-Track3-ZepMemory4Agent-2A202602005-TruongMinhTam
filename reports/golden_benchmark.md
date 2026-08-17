# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **20/20**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1200.4 ms**
- Average token reduction vs full source context: **2.5%**
- Golden bonus: **10/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.2 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.0 | 133 | 0.0% |  |
| G06 | long_term | PASS | 1502.2 | 855 | 0.0% |  |
| G09 | semantic | PASS | 239.4 | 418 | 8.9% |  |
| G10 | semantic | PASS | 226.9 | 270 | 41.2% |  |
| G14 | mixed | PASS | 1673.7 | 1069 | 0.0% |  |
| G03 | long_term | PASS | 1497.7 | 1567 | 0.0% |  |
| G04 | long_term | PASS | 1616.3 | 1543 | 0.0% |  |
| G07 | episodic | PASS | 348.3 | 565 | 0.0% |  |
| G08 | episodic | PASS | 299.7 | 604 | 0.0% |  |
| G11 | mixed | PASS | 1836.7 | 1262 | 0.0% |  |
| G13 | mixed | PASS | 523.0 | 1020 | 0.0% |  |
| G15 | mixed | PASS | 1968.3 | 1947 | 0.0% |  |
| G16 | mixed | PASS | 1720.7 | 1395 | 0.0% |  |
| G17 | mixed | PASS | 1968.4 | 1395 | 0.0% |  |
| G18 | mixed | PASS | 580.7 | 875 | 0.0% |  |
| G19 | mixed | PASS | 2013.7 | 1427 | 0.0% |  |
| G05 | long_term | PASS | 1755.8 | 1350 | 0.0% |  |
| G12 | mixed | PASS | 2110.7 | 1200 | 0.0% |  |
| G20 | mixed | PASS | 2125.5 | 1430 | 0.0% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G06 - long_term

`EPISODE: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend. EPISODE: Da hieu: LOTUS-88, Java + Spring Boot cho backend examples. EPISODE: Minh la Lan, phap ly hoi gat truoc khi bat memory tren san pham. Viet hop dong ngan: backend minh dang dung ngon ngu/framework nao, va quy tac luu/xoa bo nho ca nhan trong lab yeu cau opt-in va verify ra sao? Chi stack cua Lan.  <USER_SUMMARY> Lan's project is LOTUS-88. They prioritize Java and Spring Boot for backend development and do not use Python. </USER_SUMMARY>  <FACTS> The timestamp shown for each fact is the reference time of the source message that introduced it — i.e. when the fact w`

### G09 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal `

### G10 - semantic

`EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. metadata= EPISODE: {"id":"kb-context-budget","entity":"Memory Context Budget","summary":"Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodi`

### G14 - mixed

`<LONG_TERM> EPISODE: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend. EPISODE: Da hieu: LOTUS-88, Java + Spring Boot cho backend examples.  <USER_SUMMARY> Lan's project is LOTUS-88. They prioritize Java and Spring Boot for backend development and do not use Python. </USER_SUMMARY>  <FACTS> The timestamp shown for each fact is the reference time of the source message that introduced it — i.e. when the fact was first mentioned. `date unknown` means no reference time is recorded for the source message.   - The Lab Assistant mentioned Spring Boot. (2026-08-01 11:00:20)   - Lan Tran prefers Spring Boot. (2026-08-01 11:00:00)   - Jav`

### G03 - long_term

`EPISODE: Toi nay minh viet tool ca nhan de tai hien su co HTTP roi sua dung playbook. Can ba manh: ngon ngu minh thich khi lam mot minh, ma su co async lan truoc, va buoc playbook truoc khi tang timeout. Scope Minh, dung tron Lan. EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh. EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread, stack bat buoc cua backend cong ty, va cach danh dau request payment de khong trung don`

### G04 - long_term

`EPISODE: Toi nay minh viet tool ca nhan de tai hien su co HTTP roi sua dung playbook. Can ba manh: ngon ngu minh thich khi lam mot minh, ma su co async lan truoc, va buoc playbook truoc khi tang timeout. Scope Minh, dung tron Lan. EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh. EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread, stack bat buoc cua backend cong ty, va cach danh dau request payment de khong trung don`

### G07 - episodic

`EPISODE: Toi nay minh viet tool ca nhan de tai hien su co HTTP roi sua dung playbook. Can ba manh: ngon ngu minh thich khi lam mot minh, ma su co async lan truoc, va buoc playbook truoc khi EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread EPISODE: Minh con open loop hay deadline nao chua hoan thanh? EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va`

### G08 - episodic

`EPISODE: Toi nay minh viet tool ca nhan de tai hien su co HTTP roi sua dung playbook. Can ba manh: ngon ngu minh thich khi lam mot minh, ma su co async lan truoc, va buoc playbook truoc khi EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. E`

### G11 - mixed

`<LONG_TERM> EPISODE: Toi nay minh viet tool ca nhan de tai hien su co HTTP roi sua dung playbook. Can ba manh: ngon ngu minh thich khi lam mot minh, ma su co async lan truoc, va buoc playbook truoc khi tang timeout. Scope Minh, dung tron Lan. EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh. EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread, stack bat buoc cua backend cong ty, va cach danh dau request payment de kho`

### G13 - mixed

`<EPISODIC> EPISODE: Toi nay minh viet tool ca nhan de tai hien su co HTTP roi sua dung playbook. Can ba manh: ngon ngu minh thich khi lam mot minh, ma su co async lan truoc, va buoc playbook truoc khi EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi`

### G15 - mixed

`<LONG_TERM> EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh. EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread, stack bat buoc cua backend cong ty, va cach danh dau request payment de khong trung don. EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de`

### G16 - mixed

`<LONG_TERM> EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh. EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread, stack bat buoc cua backend cong ty, va cach danh dau request payment de khong trung don. EPISODE: Minh con open loop hay deadline nao chua hoan thanh? EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Toi dang hoc asyn`

### G17 - mixed

`<LONG_TERM> EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh. EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread, stack bat buoc cua backend cong ty, va cach danh dau request payment de khong trung don. EPISODE: Minh con open loop hay deadline nao chua hoan thanh? EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Da hieu: demo ca `

### G18 - mixed

`<EPISODIC> EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay `

### G19 - mixed

`<LONG_TERM> EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread, stack bat buoc cua backend cong ty, va cach danh dau request payment de khong trung don. EPISODE: Minh con open loop hay deadline nao chua hoan thanh? EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. EPISODE: Hom nay toi debug async `

### G05 - long_term

`EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread, stack bat buoc cua backend cong ty, va cach danh dau request payment de khong trung don. EPISODE: Minh con open loop hay deadline nao chua hoan thanh? EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: Toi se uu tien`

### G12 - mixed

`<LONG_TERM> EPISODE: Trong thread nay minh vua nhac constraint gio standup. Lat nua minh se them retry payment vao dung backend du an cong ty. Ghep ba manh: constraint standup con hieu luc trong thread, stack bat buoc cua backend cong ty, va cach danh dau request payment de khong trung don. EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: Toi se uu tien timeline khi giai thich coroutine va Task. EPISOD`

### G20 - mixed

`<SHORT_TERM> <SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Filler about dashboard widgets. | assistant: Filler. | user: Filler about CSS variables. | assistant: Filler. | user: Filler about copy review. | assistant: Filler. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. </DURABLE_NOTES> <RECENT_TURNS> user: Filler about empty charts. assistant: Filler. user: Filler about telemetry. assistant: Filler. user: Filler about a11y labels. assistant: Filler. </RECENT_TURNS> </SHORT_TERM>`
