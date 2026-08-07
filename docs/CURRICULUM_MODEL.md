# Curriculum model

The handbook is an interview preparation resource first and an Android reference second.

> One page answers one realistic interview question.

A reader should quickly learn what to say, why it is correct, where it applies, and what follow-up questions may come next. The handbook must not recreate the Android documentation or turn every question into a platform architecture chapter.

## Primary content type

Most pages are `interview-question` pages. Each one should be searchable and recognizable as something a candidate may realistically be asked during an Android, Kotlin, architecture, coding, system-design, debugging, or project-discussion round.

Examples:

- What is Context?
- What is the difference between StateFlow and SharedFlow?
- When would you choose MVVM over MVI?
- How should authentication tokens be stored?
- How would you design an offline-first data layer?

## Three curriculum tracks

### Core

Questions candidates should prepare first. These include common Android fundamentals, Kotlin, coroutines, Compose, architecture, networking, persistence, testing, and practical production scenarios.

### Advanced

Likely senior follow-ups, difficult trade-offs, failure modes, and production judgment. Advanced does not mean "longer documentation". It means the interviewer can use the question to test depth.

### Reference

Optional supporting material that helps explain an answer but is unlikely to be the direct interview question. Reference material should normally live in a separate deep-dive or reference page.

## Inclusion test

Before adding a standalone page, ask:

1. Could an interviewer realistically ask this directly?
2. Is it a likely follow-up to a realistic question?
3. Does it test an Android use case, feature, language concept, design pattern, debugging skill, trade-off, or engineering decision?
4. Would a candidate plausibly search for this while preparing for an interview?

If the answer is no, it probably does not belong as an interview question.

## Page scope

A question page should normally contain:

1. An interview-ready answer that can be spoken in 30–60 seconds
2. What the interviewer is testing
3. A common interview mistake when useful
4. A brief elaboration only when the interviewer asks for more depth
5. A focused code sample when useful
6. Likely follow-up questions
7. What separates a senior answer when that distinction is meaningful
8. Key takeaways

Do not add an internal-implementation section by default. Add internals only when they are necessary to explain the interview answer. Move substantial internals into a separate deep dive.

## Question inventory

`QUESTION_INVENTORY.md` is a generated planning and review index. Keep it because it makes stable IDs, scope, and placeholder coverage auditable, but do not treat it as a second content source or edit it independently. `SYLLABUS.md` explains curriculum priorities. The content directories and stable IDs are the source of truth for authored pages.

## Frequency claims

Do not invent frequency labels, company tags, or claims that a question is "always asked." Frequency metadata may be introduced later only with a documented research method.
