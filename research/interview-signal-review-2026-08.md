# Android interview signal review — August 2026

## Purpose

This note records public evidence used to refine syllabus priority. It is not a statistical frequency study and must not be presented to readers as proof that a specific company will ask a specific question.

## Signals observed

Recent public interview reports and question collections repeatedly surface:

- Kotlin fundamentals and coroutines, including `launch` versus `async`, dispatchers, suspension, cancellation, and Flow;
- Jetpack Compose, especially recomposition, state, side effects, state sharing, and navigation;
- architecture discussions involving MVVM, MVI, repositories, use cases, dependency injection, and modularisation;
- Android fundamentals such as lifecycle, components, process and thread behaviour, and ANRs;
- networking, Retrofit/OkHttp, Room, paging, and offline-first design;
- foreground services, background work, and production constraints;
- testing and discussion of past projects;
- scenario-based and mobile system-design questions in senior interviews.

Low-level platform topics such as Binder internals, HAL implementation, `system_server`, and detailed ART artefacts are valuable, but the available reports more often support treating them as follow-ups or reference material rather than first-priority opening questions.

## Public sources reviewed

- Glassdoor Android developer interview reports, including reports mentioning Kotlin coroutines, Compose, MVVM/MVI, Retrofit, foreground services, offline-first design, testing, Flow, and dependency injection.
- LinkedIn public posts and articles collecting modern Compose, Coroutines, Flow, scenario-based, and mobile-system-design prompts.
- Public Android interview question repositories and recent question collections used only as supporting signals, not authoritative technical references.

## Editorial consequences

1. Keep the first reading path short and answerable aloud.
2. Prioritise Kotlin, Coroutines/Flow, Compose, lifecycle/state, architecture, testing, networking, persistence, and project discussion early.
3. Treat platform internals as advanced follow-ups or linked deep dives unless they directly explain a common interview question.
4. Include scenario, debugging, coding, and project-deep-dive preparation rather than building only definition pages.
5. Do not add company tags or frequency ratings without a documented methodology and enough evidence.
