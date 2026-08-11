# Handbook authoring guide

## Heading hierarchy

Fumadocs renders the page title from the frontmatter `title` field. Do not repeat it as a level-one Markdown heading inside the MDX body. Begin question pages with the `<ShortAnswer>` component. The component already identifies the interview-ready answer in the rendered site, so do not add a duplicate heading above it.

Use only one reader-visible page title. Repeating the title in the body creates duplicate headings, an unnecessary table-of-contents entry, and a weaker visual hierarchy.

## One question, one file

Every interview question has one stable ID, one readable slug, and one MDX file. Category introductions use `index.mdx` and do not need question IDs.

Category `index.mdx` files must not maintain a manual `## Questions` list. The site generates that list from interview-question pages in the same section whose frontmatter is `status: published`, ordered by question ID. Publishing a new question therefore updates its section page automatically.

The handbook landing page must not maintain a manual Question groups link list. Keep the `## Question groups` heading in `handbook/content/index.mdx` and render `<PublishedQuestionGroups />` beneath it. The component derives the links from published section landing pages that contain at least one `status: published` interview question, using the handbook section order from `handbook/content/meta.json`. Publishing the first question in a section therefore makes that question group eligible to appear automatically.

A contributor should be able to add or improve one question in a small, reviewable pull request.

## Frontmatter

```yaml
---
id: COR-011
title: What is the difference between StateFlow and SharedFlow?
description: Compare their state, replay, and event-delivery behaviour.
difficulty: intermediate
track: core
contentType: interview-question
estimatedTime: 6
answerTime: "~30 sec"
status: draft
tags:
  - stateflow
  - sharedflow
prerequisites: []
related: []
---
```

Allowed difficulty values:

- `foundational`
- `intermediate`
- `advanced`
- `senior`
- `staff`

Allowed track values:

- `core`
- `advanced`
- `reference`

Allowed status values:

- `draft`
- `review`
- `published`

## Required editorial shape

Use `templates/question-template.mdx` as the starting point. The default shape is deliberately compact:

- Interview-ready answer in `<ShortAnswer>` with no duplicate heading
- What the interviewer is testing
- Common interview mistake when useful
- If they ask you to elaborate
- Optional code example with a brief explanation when useful
- Follow-up questions linked to existing handbook pages; draft/review destinations are automatically hidden until published
- Remember statement when one sentence captures the mental model
- What separates a senior answer when meaningful
- Key takeaways
- Learn more with verified references

Do not add a deep-dive section automatically. Link to a separate deep dive when substantial internal detail is genuinely useful.

## Placeholder policy

The initial foundation contains draft placeholder files with HTML authoring comments. Placeholders must remain `draft`. Replace comments with reviewed reader-facing content before changing status.

## Contribution workflow

1. Choose an existing draft placeholder from `content/`, or propose a realistic missing interview question.
2. Confirm the stable ID and category.
3. Research authoritative technical sources.
4. Write the short answer first.
5. Add only enough explanation and code to support that answer. For production examples, explain the decision and failure mode rather than narrating the API.
6. Add a short set of realistic follow-ups that already have handbook pages, and link them directly. Draft/review targets will stay hidden until published.
7. Run validation and inspect the rendered page.
8. Submit one focused question or tightly related correction per pull request when practical.

## GitHub readability

The public repository must remain useful without the DevBits website. Essential meaning belongs in Markdown headings and prose, not site-private components.


## Defining a senior answer

A senior answer is not one that mentions more APIs.

A senior answer demonstrates engineering judgement by discussing ownership, lifecycle, boundaries, trade-offs, production implications, and why one solution is preferable in context.

The goal is to teach how experienced engineers think, not simply what they know.


## Engineering Questions vs Interview Questions

The interview question is the entry point, not the lesson.

When proposing or drafting a page, identify the **hidden engineering question** the interviewer is really trying to evaluate.

Examples:

- **Interview question:** What are Compose side-effect APIs?
  - **Hidden engineering question:** Does the candidate understand the boundary between describing the UI and making the application do work?

- **Interview question:** What is state hoisting?
  - **Hidden engineering question:** Does the candidate understand ownership?

- **Interview question:** remember vs rememberSaveable
  - **Hidden engineering question:** Does the candidate understand state lifetime?

- **Interview question:** collectAsStateWithLifecycle
  - **Hidden engineering question:** Does the candidate understand lifecycle ownership?

Teach the engineering question first. Let the technology appear naturally as the solution.

### Technology-first vs Problem-first

Not every page should be written the same way.

**Category A – Technology-first**

The technology itself is the lesson (for example: `val` vs `var`, `lateinit` vs `lazy`, `remember` vs `rememberSaveable`).

**Category B – Problem-first**

The technology exists because it solves a broader engineering problem (for example: ViewModel, side effects, WorkManager, Navigation, Lifecycle, Room, StateFlow).

For Category B pages:

1. Identify the engineering problem.
2. Explain why it exists using real production situations.
3. Build the mental model.
4. Introduce the technology as one solution.
5. Use APIs and implementation details to reinforce the mental model, not replace it.
6. In Production Thinking, walk through realistic choices the way engineers would during pair programming or review: establish why the work belongs at that boundary, why the chosen approach fits, and what failure a different choice would create.


### Production examples should expose the decision

When a page needs real-world code, do not stop at showing a plausible snippet and explaining what the API does. Make the engineering decision behind the code visible.

For each substantial production example, contributors and reviewers should be able to answer:

- Why does this work belong here?
- Why is this API or approach appropriate for that ownership and lifetime?
- What would go wrong if the work were started, stored, observed, or cleaned up differently?

These are drafting and review questions, not mandatory reader-facing headings. The final explanation should read like a useful engineering conversation: concrete, contextual, and focused on the decision. Introduce API behaviour only to the depth needed to make that decision understandable.

This rule applies beyond Compose. A ViewModel example might expose ownership; a coroutine example might expose cancellation; a Room example might expose consistency or source-of-truth boundaries. The technology changes, but the review style remains the same.

### Keep the interview question realistic

The hidden engineering question guides the lesson; it does **not** replace the interview question.

Question titles should still sound like something an interviewer could plausibly ask in an Android interview. When an API-shaped question pushes the page toward documentation, prefer a broader but still realistic interview phrasing that exposes the candidate's reasoning.

Prefer:

> What are side effects in Compose and how should they be handled?

Over:

> What are the Compose side-effect APIs and when do you use them?

The first question can still lead to `LaunchedEffect`, `DisposableEffect`, and the other APIs, but it gives the candidate room to explain the problem before naming solutions.

Do not broaden a question so far that it stops resembling an interview question. The handbook remains interview-first.

### The API removal test

Before drafting a problem-first page, temporarily remove the framework and API names from the explanation and ask:

> Would the engineering lesson still make sense?

If the answer is no, the page is probably teaching the mechanism before the problem.

For example, a Compose side-effects page should still make sense without `LaunchedEffect` or `DisposableEffect`: real UI code sometimes needs to perform actions, those actions have owners and lifetimes, some should restart, and some require cleanup. The APIs can then be introduced as ways Compose gives those actions predictable behaviour.
