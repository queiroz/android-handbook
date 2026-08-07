# Android Interview Handbook

An interview-first engineering handbook for Android developers.

The handbook uses realistic interview questions as the entry point, but its broader goal is to teach the mental models, trade-offs, and production judgement used by experienced Android engineers. It covers Android platform fundamentals together with Kotlin, coroutines and Flow, Jetpack Compose, architecture, networking, persistence, security, testing, performance, system design, and senior engineering practice.

A reader should leave each page able to:

- answer the interview question clearly and naturally;
- explain why the concept or design exists;
- recognise the production problems it solves;
- understand the boundaries and trade-offs a senior engineer considers; and
- return later to refresh the mental model, not only memorise an answer.

This is not a rewrite of official documentation. API details and platform internals are included only when they support the interview question or the engineering model behind it.



## DevBits Manifesto

The DevBits Handbook teaches **engineering judgement through interview questions**.

Interview questions are the entry point—not the destination.

Every page should leave the reader with:

- a better interview answer;
- a deeper understanding of *why* the technology exists;
- one transferable engineering concept;
- practical production judgement; and
- a mental model that remains valuable even if the APIs evolve.

We do not compete with official documentation.

Documentation explains **how** an API works.

DevBits explains **why** it exists, **what problem it solves**, and **how experienced engineers reason about it**.

### Our golden rule

> **Teach the reasoning, not just the mechanism.**

When writing a page, explain the engineering problem before introducing the framework, language feature, or library that solves it.

If a reader understands only the API, the page is incomplete.

If they understand the underlying engineering idea, the page has succeeded.

## Repository structure

```text
content/                  Canonical MDX question pages grouped by domain
QUESTION_INVENTORY.md     Generated planning inventory of stable question IDs
SYLLABUS.md               Curriculum priorities and study order
CONTRIBUTING.md           Public contribution rules
docs/                     Authoring, writing, IDs, references, and publication policy
templates/                Reusable question templates
assets/ and diagrams/     Handbook-owned visual resources
```

The contents of this directory are designed to become the standalone public `android-interview-handbook` repository. The private DevBits website remains separate and renders this portable content.

## Sources of truth

- Authored pages and stable IDs: [`content/`](./content/)
- Curriculum priorities: [`SYLLABUS.md`](./SYLLABUS.md)
- Planning inventory: [`QUESTION_INVENTORY.md`](./QUESTION_INVENTORY.md)
- Editorial model: [`docs/WRITING_GUIDE.md`](./docs/WRITING_GUIDE.md)
- MDX and metadata rules: [`docs/AUTHORING.md`](./docs/AUTHORING.md)
- Reference requirements: [`docs/REFERENCE_POLICY.md`](./docs/REFERENCE_POLICY.md)

`QUESTION_INVENTORY.md` is useful as a generated planning and review index. It is not the canonical content source and should not be edited independently of the content tree and stable IDs.

## Contributing

Read [`CONTRIBUTING.md`](./CONTRIBUTING.md) before proposing or editing a question. Start from [`templates/question-template.mdx`](./templates/question-template.mdx) and keep every page portable and readable outside the DevBits renderer.
