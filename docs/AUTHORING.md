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
5. Add only enough explanation and code to support that answer.
6. Add a short set of realistic follow-ups that already have handbook pages, and link them directly. Draft/review targets will stay hidden until published.
7. Run validation and inspect the rendered page.
8. Submit one focused question or tightly related correction per pull request when practical.

## GitHub readability

The public repository must remain useful without the DevBits website. Essential meaning belongs in Markdown headings and prose, not site-private components.


## Defining a senior answer

A senior answer is not one that mentions more APIs.

A senior answer demonstrates engineering judgement by discussing ownership, lifecycle, boundaries, trade-offs, production implications, and why one solution is preferable in context.

The goal is to teach how experienced engineers think, not simply what they know.
