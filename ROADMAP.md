# Android Interview Handbook roadmap

The roadmap is milestone-based rather than date-driven. Technical trust, interview relevance, and a coherent study path matter more than page count. Work is prioritized through the Core, Advanced, and Reference tracks defined in `docs/CURRICULUM_MODEL.md`.

## 0.1 — Foundation and Android Runtime

- Define the master syllabus and stable question-ID namespaces
- Complete Android platform architecture and runtime foundations
- Cover processes, Zygote, Dalvik, ART, DEX, JIT, AOT, profiles, GC, APK, AAB, Multidex, and startup modes
- Add checked primary references to every published page
- Establish a glossary and cross-reference conventions

## 0.2 — Kotlin

- Language fundamentals and null safety
- Objects, data classes, sealed hierarchies, and companion objects
- Lambdas, higher-order functions, collections, and sequences
- Inline functions, reified types, generics, and variance
- Kotlin interview traps and focused exercises

## 0.3 — Coroutines and Flow

- Coroutines versus threads
- Suspending versus blocking
- Structured concurrency, scopes, cancellation, and failures
- Dispatchers and context switching
- Flow, StateFlow, SharedFlow, Channel, backpressure, and testing

## 0.4 — Jetpack Compose

- Composition, recomposition, and snapshots
- State ownership, hoisting, remember, and saveable state
- Stability, skipping, side effects, derived state, and snapshotFlow
- Navigation, performance, accessibility, and testing

## 0.5 — Android application model

- Activities, Fragments, lifecycle, configuration changes, and process death
- ViewModel and SavedStateHandle
- Context, Intent, Bundle, PendingIntent, Services, receivers, and providers
- Tasks, back stack, deep links, main-thread responsibilities, and ANRs

## 0.6 — Production architecture

- MVVM, MVI, repositories, use cases, and Clean Architecture trade-offs
- Dependency injection and modularization
- Retrofit, OkHttp, Room, DataStore, Paging, offline-first, and WorkManager

## 0.7 — Senior production concerns

- Security, tokens, TLS, certificate pinning, and secure storage
- Startup, memory, jank, battery, Baseline Profiles, Macrobenchmark, and Perfetto
- Unit, integration, UI, Compose, Flow, and coroutine testing
- CI/CD, releases, observability, and incident learning

## 0.8 — Interview practice

- Mobile system design
- Architecture exercises
- Coding exercises and interview traps
- Leadership and behavioural questions
- Mock interview scripts and scoring rubrics

## 1.0 — Reviewed senior Android handbook

Version 1.0 means the core curriculum is coherent, technically reviewed, referenced, navigable, and useful for structured senior Android interview preparation.


## Writing Standard
All future content follows `handbook/docs/WRITING_GUIDE.md`.
