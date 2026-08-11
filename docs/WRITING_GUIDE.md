# Writing guide

## Purpose

The handbook uses realistic industry and interview questions to help developers prepare for interviews **and** become stronger Android engineers.

It covers Android together with Kotlin, coroutines and Flow, Jetpack Compose, architecture, networking, persistence, security, testing, performance, system design, and senior engineering practice.

Each page should work in two ways:

1. help a candidate answer the question clearly under interview pressure; and
2. teach a durable mental model the reader can revisit when solving or relearning the topic in production.

This is not API documentation, a textbook chapter, or a collection of answers to memorise.



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

## Authorial perspective

Write like an experienced senior engineer mentoring another developer.

- Friendly, direct, and practical
- Technically precise without sounding academic
- Brief before deep
- Clear about ownership, lifecycle, boundaries, failure modes, and trade-offs
- Honest about version differences and uncertainty
- Free of filler, artificial drama, canned phrasing, and unsupported seniority claims

A useful test is:

> Would this feel like a thoughtful explanation from a senior teammate, and could the reader still say the opening answer naturally in an interview?

## The central mental model

Every page should have one primary idea the reader can remember after the API details fade.

Examples:

- Android is an operating system **and** an application platform.
- Context is access to Android-managed capabilities.
- Compare Activities and Fragments by responsibility, not size.
- The Fragment can survive while its View is disposable.
- For Intents, ask who chooses the destination.
- A PendingIntent delegates permission for one predefined action.
- A Bundle carries transient state; it does not own or persist it.

Every section should reinforce that model. If a section introduces a second large lesson, it probably belongs in a follow-up question or reference page.

## Interview-first page order

The direct spoken answer comes first. Readers should not need to study internals before learning what they should say.

A typical page uses:

1. **Interview-ready answer** — concise enough to say in about 30 seconds.
2. **What the interviewer is testing** — the hidden capability, mental model, or judgement behind the question.
3. **Common interview mistake** — one or two realistic misconceptions when useful.
4. **If they ask you to elaborate** — the smallest useful explanation of the problem, mental model, trade-off, or scenario.
5. **Code example** — optional; only when a compact snippet materially improves understanding.
6. **Remember** — recommended when one sentence captures the core model.
7. **Follow-up questions** — a short list of existing handbook pages.
8. **What separates a senior answer** — production judgement, boundaries, and knowing when to stop.
9. **Key takeaways** — a compact revision summary.
10. **Learn more** — authoritative sources.

This is a model, not a quota. Remove sections that do not help the specific question.

## Problem first, API second

The page begins with the interview-ready answer. Within the explanation, teach the problem and design reasoning before cataloguing APIs.

Prefer:

> Android sometimes needs another process to trigger one predefined action, so it uses PendingIntent as delegated permission.

Over:

> PendingIntent has these factory methods and flags.

Prefer:

> Android reuses Bundle as a small transport container across framework boundaries.

Over:

> Bundle supports these value types and methods.

The API should confirm the mental model, not become the mental model.



## Engineering-first philosophy

The handbook teaches engineering judgement through interview questions. APIs, libraries, and frameworks are the vehicles—not the destination.

For every topic, explain:
- What problem existed?
- Why was this solution introduced?
- What transferable engineering concept does it teach?
- What production trade-offs exist?
- How would an experienced engineer reason about this?

Readers should finish a page understanding a way of thinking, not just a way of coding.

## Universal questions every page should answer

Regardless of subject (Android, Kotlin, Coroutines, Compose, Architecture, Testing, Networking or Security), naturally answer:

1. What problem existed?
2. Why was this solution introduced?
3. What mental model should I remember?
4. What engineering judgement does a senior developer apply?
5. How does this appear in production?

## Recurring engineering themes

Reinforce recurring ideas whenever they naturally fit:

- Ownership
- Lifetime
- Responsibility
- Boundaries
- Source of truth
- State
- Immutability
- Delegation
- Separation of concerns
- Trade-offs
- Failure handling

These concepts intentionally repeat across different technologies to help readers build durable intuition instead of isolated facts.

## Teach decisions, not APIs

Avoid turning pages into API catalogues or feature comparisons.

Explain why experienced engineers choose one approach over another, what trade-offs they consider, and what the interviewer is really evaluating.

## The "rename the API" test

Before publishing, ask:

> If this API were renamed tomorrow, would the page still teach something valuable?

If the answer is no, the page probably explains the mechanism but not the underlying engineering concept.

For problem-first questions, also use the **API removal test** while drafting:

> If the API names disappeared from the explanation, would the reader still understand the problem, the ownership boundary, and the decision being made?

The answer should be yes before implementation details are introduced. This prevents API-shaped interview questions from turning into API catalogues.

The hidden engineering question should shape the explanation, but the visible title must still be a realistic interview question. Prefer wording that lets a candidate explain reasoning before listing mechanisms.

## The 80/20 scope rule

Include the small amount of knowledge needed to answer the question confidently and reason about it in production. Move the remaining detail into follow-up questions, deep dives, or official references.

One page answers one realistic question. Do not:

- reproduce official documentation;
- explain every method, flag, callback, or implementation detail;
- add history or internals merely to appear comprehensive;
- turn likely follow-up questions into subsections of the current page; or
- force code, diagrams, or tables into every lesson.

A page is probably doing too much when the reader can no longer identify its one central mental model.

## Interview-ready answers

A good opening answer should:

- answer the exact question immediately;
- sound natural when spoken;
- use terminology the candidate can explain under follow-up;
- mention the most important use case, boundary, or caveat;
- avoid dumping every fact the writer knows; and
- fit comfortably into roughly 30 seconds unless the question genuinely requires more.

Do not confuse simplicity with incompleteness. The elaboration exists for the next question.

## Explanations and scenarios

Use the smallest scenario that makes the design inevitable. Good explanations often ask:

- Who owns this state, action, window, or lifecycle?
- What survives, and what can be recreated?
- Which process or layer is responsible?
- Is this transport, storage, execution, or ownership?
- What failure appears when the boundary is misunderstood?

Short decision tables, lifecycle sequences, or diagrams are useful when they replace prose. Do not use them as decoration.

## Code examples

Code is optional. Include it only when it demonstrates one idea more clearly than prose.

A useful sample should:

- be small enough to discuss aloud;
- omit unrelated setup and boilerplate;
- model a production-worthy decision rather than a toy trick; and
- be followed by the reasoning a reviewer would care about, not a line-by-line description of the API.

When code represents a real production decision, explain it as if reviewing the change with another engineer. The useful question is rarely only *what does this API do?* It is usually *why does this work belong here, why is this mechanism a good fit, and what bug or maintenance problem would another choice create?*

Typical guidance:

| Question type | Include code? |
| --- | --- |
| API usage | Usually |
| Lifecycle | Often |
| Architecture | Often |
| Kotlin language features | Usually |
| Conceptual definitions | Only if it adds value |
| Comparisons | Usually not |
| Historical/background questions | No |

Never add code because the template has a slot.

## Production judgement

The handbook should connect concepts to realistic engineering consequences without becoming a troubleshooting encyclopedia.

Examples include:

- retaining the wrong Context and leaking a screen;
- observing a Fragment longer than its View exists;
- reusing the wrong PendingIntent;
- treating Bundle as storage and exceeding transaction limits;
- confusing configuration change with process death;
- blocking the main thread or breaking structured concurrency;
- leaking state ownership across architecture layers.

Explain the failure and the decision that prevents it. Keep unrelated edge cases in follow-up pages.

### Production thinking should feel like collaborative engineering

Production Thinking is not the place to restate API documentation. It should show the reader how engineers reason through a real change together.

When a realistic example is useful, write it the way a good teammate would discuss the change during pair programming or review: start with what the application is trying to do, establish the boundary and consequences, then let the implementation follow from that reasoning.

A strong example should naturally answer three questions:

1. **Why does this work belong here?** — establish ownership and the boundary responsible for the work.
2. **Why is this approach appropriate?** — connect the mechanism to the required lifetime, trigger, cleanup, state, or failure behaviour.
3. **What would go wrong with a different approach?** — name the duplicate work, leak, stale value, incorrect lifetime, hidden coupling, or other production consequence the decision avoids.

Do not force those questions into visible labels on every page. Use them as a review test while drafting. The finished prose should feel like one engineer walking another through the decision:

> Before choosing the API, ask why this work belongs to the screen. Once ownership and lifetime are clear, the API choice usually becomes much easier to explain.

Prefer this style:

> The listener belongs to this screen, but only while the screen is present. The important part is not registering it; it is guaranteeing that it is removed when the UI goes away. This mechanism gives us both setup and cleanup at the same boundary, so the listener cannot quietly outlive the screen.

Over this style:

> This API registers a listener and invokes cleanup when the composable leaves Composition.

The second sentence may be technically correct, but it teaches the mechanism. The first teaches ownership, lifetime, and the failure the API prevents.

For unfamiliar APIs, one short sentence about the relevant behaviour is enough when the reader needs it to understand the decision. Junior and returning engineers should understand *why the code works*; experienced readers should not have to read a miniature reference manual.

The goal is not to make every Production Thinking section longer. Use as many real examples as the interview question genuinely needs, and make each example earn its place by teaching a distinct decision.

## What separates a senior answer

Describe the qualities that demonstrate depth:

- precise terminology;
- a clear mental model;
- ownership and lifecycle awareness;
- appropriate trade-offs;
- production failure awareness;
- modern platform or language practice; and
- knowing when the answer is complete.

Do not turn this into a generic junior/mid/senior ladder. Seniority is shown through judgement, not the number of facts listed.

## Follow-up questions

Follow-ups are navigation, not a wish list. Include only questions with existing handbook pages and link them directly. Three to five useful branches are usually enough.

If the elaboration starts fully answering another interview question, stop and link to it.

## Remember statements

After the elaboration, use `<Remember>` when one sentence captures the page's core model.

The statement should be short enough to recall during an interview and useful enough to guide production reasoning.

Do not repeat the same sentence in the paragraph immediately before or after the callout.

## Semantic callout colours

Callout colours form a consistent visual language. Choose components by meaning, not decoration.

| Component | Visual tone | Meaning |
| --- | --- | --- |
| `<ShortAnswer>` | Green | The answer the candidate should be able to say aloud |
| `<CommonMistake>` | Amber | A realistic misconception or risky practice |
| `<Remember>` | Blue | One memorable mental model or interview shortcut |
| `<FollowUp>` | Teal | Existing questions that naturally continue the interview |
| `<SeniorAnswer>` | Indigo | Judgement, boundaries, and trade-offs that distinguish a strong senior answer |
| `<KeyTakeaways>` | Purple | Fast revision at the end of the page |
| Code block | Neutral | Practical implementation without semantic callout colouring |

## Accuracy and industry relevance

Use primary technical sources for claims: official Android, AOSP, Kotlin, kotlinx.coroutines, Jetpack, standards, and first-party engineering material.

Industry and interview research may help choose and frame questions, but do not invent frequency, company, or hiring claims. Treat anonymous interview reports and community discussions as signals, not authoritative technical evidence.

Qualify version-dependent behaviour. Never present private implementation detail as a permanent public guarantee.

## Finished page checklist

Before considering a page complete, verify:

- The opening answer can be spoken naturally in about 30 seconds.
- The page has one clear mental model.
- The reader understands why the concept or decision exists.
- The explanation goes only one useful level deeper.
- The page teaches production judgement without becoming documentation.
- Real-world examples explain ownership, why the chosen approach fits, and what failure it prevents.
- Production Thinking reads like collaborative engineering discussion, not an API walkthrough.
- Code exists only if it materially improves understanding.
- The Remember callout does not duplicate nearby prose.
- Follow-ups link to existing pages.
- Key takeaways fit comfortably on one screen.
- Learn more contains opened and verified authoritative sources.
- The page is useful both for interview revision and for relearning the engineering topic later.


### Answer the interview question, not the subject

Every page answers a single interview question, not an entire technology. Resist turning a question into a mini-guide for the framework. The interview-ready answer should answer the interviewer's question first; deeper concepts belong later on the page or in follow-up questions.


## Prefer concrete problems over technical vocabulary

Prefer describing what the application is trying to do before introducing framework terminology.

Instead of abstract phrases like "imperative work", use concrete examples:

- show a Snackbar
- navigate to another screen
- register a listener
- start a coroutine
- send analytics

Once the reader understands the problem, introduce the technical term only if it genuinely improves understanding.

## Writing order

For every handbook page:

1. Find the hidden engineering question.
2. Explain the real production problem.
3. Build the mental model.
4. Answer the interview question.
5. Discuss production thinking and trade-offs.
6. Introduce APIs and implementation details as practical solutions.

Readers should understand *why* before learning *how*.
