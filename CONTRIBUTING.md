# Contributing to the Android Interview Handbook

Contributions should help Android developers answer realistic interview questions confidently and understand the reasoning behind those answers. Adding more pages is not the goal; adding useful, accurate, focused interview preparation is.

## Before contributing

1. Search existing questions and open proposals to avoid duplicates.
2. Read [`docs/AUTHORING.md`](./docs/AUTHORING.md) and [`docs/WRITING_GUIDE.md`](./docs/WRITING_GUIDE.md).
3. Follow the stable ID rules in [`docs/QUESTION_IDS.md`](./docs/QUESTION_IDS.md).
4. Verify sources using [`docs/REFERENCE_POLICY.md`](./docs/REFERENCE_POLICY.md).
5. Start from [`templates/question-template.mdx`](./templates/question-template.mdx).

## The interview-question model

One page answers one realistic interview question. The page should feel like a short interview conversation, not a documentation chapter.

The default order is:

1. **Interview-ready answer** — the answer the candidate can say naturally in roughly about 30 seconds.
2. **What the interviewer is testing** — the capability, mental model, or engineering judgement behind the question.
3. **Common mistake** — one or two realistic mistakes when this adds value.
4. **If they ask you to elaborate** — only the smallest useful explanation, trade-off, diagram, or example.
5. **Code example** — only when code makes the answer clearer.
6. **Follow-up questions** — likely next branches of the interview. Include only questions that already have handbook pages, and link to them directly.
7. **What separates a senior answer** — the qualities that make an answer sound precise, thoughtful, and appropriately scoped.
8. **Key takeaways** — a short revision summary.
9. **Learn more** — authoritative sources and useful supporting material for readers who want to continue.

This order is a model, not a checklist. Remove sections that would be artificial. Do not add depth merely to make a page look comprehensive.

### Expected answer time

Use `answerTime` to show how long the opening answer should take when spoken aloud. Most direct questions should target roughly about 30 seconds. `estimatedTime` remains the approximate study time for the whole page.

### The 80/20 scope rule

Keep the interview page focused on the small amount of knowledge needed to answer the question well. Put substantial platform internals, history, implementation detail, and broader architectural material into follow-up questions or separate deep-dive pages.

A useful test is:

> Could a candidate read this page in a few minutes and immediately give a clear answer aloud?

If not, the page is probably doing too much.


### Follow-up links

Follow-up questions are navigation, not a wish list. During drafting and review, a follow-up may point to another existing handbook page that is still being written. Before the current page becomes `published`, every reader-visible handbook link must also point to a `published` destination so production never exposes dead navigation. Link each visible item to its stable handbook route. Do not list an unimplemented question as plain text; add the question to the syllabus and inventory first.

Keep the list short. Three to five closely related questions are usually enough. Use core and advanced subgroups only when that split genuinely helps the reader.

### Optional examples and media

Code examples are optional. Add one only when a small, interview-discussable snippet makes the answer clearer. Remove the section for conceptual questions that do not benefit from code.

Diagrams are optional for the same reason: use them when they replace explanation, not to make a page look complete. Video embeds are not part of the current question template or MDX contract. They may be introduced later as an optional enhancement without changing the core written answer.

### Semantic callout palette

Use the supported MDX components according to meaning, not personal colour preference:

- `<ShortAnswer>` — green;
- `<CommonMistake>` — amber;
- `<Remember>` — blue;
- `<FollowUp>` — teal;
- `<SeniorAnswer>` — indigo;
- `<KeyTakeaways>` — purple;
- code blocks — neutral.

The host site owns the exact colours. Contributors own the semantic choice. Do not repeat the Remember sentence in nearby prose.

### Avoid duplicated labels

The DevBits renderer may display a label inside a callout component. Do not repeat the same label as a Markdown heading directly above it. For example, begin a question with `<ShortAnswer>` rather than adding `## Interview-ready answer` followed by a box that displays the same words.

The raw MDX must still remain understandable in GitHub. Component names and nearby prose should make their purpose clear.

## Proposing a question

Describe:

- the realistic interview question,
- why it belongs in the curriculum,
- its proposed module,
- prerequisite concepts,
- a readable slug,
- a proposed stable ID,
- and authoritative sources that support the answer.

One completed question should live in one MDX file. If the topic cannot be framed as a realistic direct question or likely follow-up, it may belong in a deep dive instead.

## Improving an answer

Explain the technical problem and keep the change focused. Preserve the distinction between the opening answer and optional elaboration. State Android-version or library-version differences when behaviour is not stable.

A strong contribution should normally:

- answer the exact question immediately,
- use language the candidate can explain under follow-up,
- include only relevant detail,
- show practical judgement when the topic requires it,
- avoid invented interview-frequency or company claims,
- and link to deeper questions instead of absorbing them into one page.

## AI-assisted submissions

AI assistance is allowed, but the contributor remains responsible for every sentence and reference. Do not submit unreviewed bulk-generated content, invented citations, repeated filler, or mass-created question shells.

## Pull requests

Keep each pull request focused. Explain how technical claims were verified and inspect the rendered page for links, headings, code blocks, accessibility, and mobile readability.

Before submitting, run the checks documented by the host project and confirm that the page reads well both as raw MDX and in the rendered handbook.
