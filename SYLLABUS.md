# Android Interview Handbook syllabus

This is the master curriculum map. It is intentionally interview-first and uses the three-track model defined in [`docs/CURRICULUM_MODEL.md`](./docs/CURRICULUM_MODEL.md).

The syllabus is developed in research-backed increments. A topic appearing here does not imply that every subtopic must become a standalone question.

## How to read this syllabus

The curriculum follows the order a candidate should study:

1. **Core interview questions** — realistic direct questions and concepts that repeatedly appear in Android, Kotlin, coding, architecture, and project-discussion rounds.
2. **Advanced follow-ups** — deeper questions that commonly follow a confident core answer or reveal production judgment.
3. **Reference deep dives** — optional internals and background material that support understanding but should not compete with core preparation time.

A broad platform topic should not automatically become one oversized interview page. Prefer a focused core question, then link to advanced follow-ups and separate deep dives where useful.

## Current interview-signal summary

A review of recent public interview reports and question collections shows a consistent modern emphasis on Kotlin and coroutines, Jetpack Compose, lifecycle and state, architecture and dependency injection, testing, networking and persistence, offline-first or background-work scenarios, and discussion of previous projects. Core Android fundamentals still appear, but low-level platform internals are more often follow-up material than opening questions.

This evidence guides prioritisation; it does not justify unsupported frequency scores or company-specific promises. Research notes and sources are recorded in [`research/interview-signal-review-2026-08.md`](./research/interview-signal-review-2026-08.md).

## Part I — Android platform and fundamentals

### Android architecture and operating-system model

Core questions:

- `AF-001` — What is Android?
- `AF-002` — What are the main layers of the Android software stack?
- `AF-003` — Where does an Android application run?
- `AF-004` — What is the difference between a process and a thread on Android?
- `AF-005` — What is the Android main thread, and why must UI work stay responsive?
- `AF-005` — What causes an ANR, and how would you diagnose one?
- `AF-007` — How are Android applications isolated from one another?
- `AF-008` — What happens at a high level when an Android application starts?

Advanced follow-ups:

- `AF-009` — What is Binder, and why does Android use it?
- `AF-010` — What is a system service, and how does an app communicate with one?
- `AF-011` — Does every Android Framework call cross a process boundary?
- `AF-012` — What is process importance, and why can Android kill an app process?

Reference deep dives:

- Zygote and process forking
- `system_server` and native service processes
- `ActivityThread` and application bootstrap
- Binder proxy, stub, transactions, and thread pools
- Hardware Abstraction Layer and kernel-driver boundaries
- memory sharing and platform process architecture

### Android Runtime

Core questions:

- `AR-001` — What is the difference between Dalvik and ART?
- `AR-002` — What is DEX and why does Android use it?
- `AR-003` — What is the difference between JIT and AOT compilation?
- `AR-005` — What is garbage collection and how can it affect Android performance?
- `AR-006` — What is Multidex and when is it relevant?

Advanced questions:

- `AR-004` — How does modern ART combine interpretation, JIT, AOT, and profiles?
- `AR-007` — What are Baseline Profiles and Cloud Profiles?
- `AR-008` — What is Zygote and how does it affect app startup and memory?

Reference deep dives:

- ART compilation lifecycle across Android releases
- DEX, OAT, VDEX, and runtime artifacts at a high level
- Android garbage-collector evolution

### Processes, threads, and responsiveness

Core themes:

- process versus thread
- Android application process model
- main thread and UI-thread confinement
- Looper, MessageQueue, and Handler
- ANRs and common causes
- thread safety and synchronization

Advanced themes:

- process importance and process death
- Binder thread pools
- memory visibility
- HandlerThread and modern alternatives

### Application lifecycle and state restoration

Core themes:

- Activity lifecycle
- Fragment lifecycle and Fragment view lifecycle
- configuration changes
- process death
- ViewModel lifecycle
- SavedStateHandle versus onSaveInstanceState
- cold, warm, and hot starts

### Android components and navigation

Core themes:

- Activity
- Fragment
- Service
- BroadcastReceiver
- ContentProvider
- Context
- Intent and intent filters
- explicit versus implicit intents
- PendingIntent
- Bundle
- deep links and app links
- tasks and back stack

Advanced themes:

- launch modes and task affinity
- bound services and IPC choices
- exported components and security boundaries

### Packaging, build, and distribution

Core themes:

- APK versus AAB
- app signing
- AndroidManifest
- resources and resource qualifiers
- R8 and shrinking
- ABI and native libraries

Advanced themes:

- dynamic feature delivery
- build variants and product flavours
- DEX limits and packaging trade-offs

## Part II — Kotlin for Android

Core themes:

- null safety and operators
- `val`, `var`, and `const val`
- `lateinit` versus `lazy`
- Any, Unit, Nothing, and Nothing?
- data classes, sealed classes, enums, and objects
- object declarations and companion objects
- lambdas and higher-order functions
- extension functions
- collections and transformations
- generics and variance
- inline and reified functions
- equality, immutability, and value semantics

Advanced themes:

- delegated properties
- contracts
- sequences
- type erasure
- value classes
- DSL design
- Java interoperability

## Part III — Coroutines and Flow

Core themes:

- coroutine versus thread
- suspending versus blocking
- structured concurrency
- launch versus async
- scopes and lifecycle-aware scopes
- Dispatchers.Main, IO, and Default
- cancellation and exception propagation
- Flow fundamentals
- StateFlow, SharedFlow, and Channel
- backpressure-related operators
- debounce, combine, zip, and latest operators

Advanced themes:

- supervisorScope and SupervisorJob
- callbackFlow and channelFlow
- stateIn and shareIn
- buffering, conflation, and cancellation semantics
- Mutex, Semaphore, and shared mutable state
- coroutine testing and virtual time

## Part IV — Jetpack Compose

Core themes:

- Compose versus the View system
- composition and recomposition
- state and state hoisting
- remember versus rememberSaveable
- side-effect APIs
- observing ViewModel state
- navigation with NavHost and NavController
- stateless versus stateful composables
- Lazy layouts
- accessibility and testing basics

Advanced themes:

- snapshot system
- stability and skipping
- derivedStateOf
- snapshotFlow
- CompositionLocal
- SaveableStateHolder
- mutableStateListOf and mutableStateMapOf
- layout, drawing, and modifier ordering
- performance diagnostics

Reference deep dives:

- snapshot isolation and mutation policies
- Compose runtime phases
- compiler stability inference

## Part V — Android architecture and design

Core themes:

- separation of concerns
- repository pattern
- UI, domain, and data layers
- MVVM
- MVI and unidirectional data flow
- MVP and MVC in historical context
- Clean Architecture
- use cases
- single source of truth
- state ownership
- error handling
- dependency inversion
- modularization

Advanced themes:

- choosing MVVM versus MVI
- when Clean Architecture is excessive
- feature-based versus layer-based modularization
- architecture boundaries and mapping models
- feature flags
- scaling code ownership
- architecture decision records

## Part VI — Dependency injection

Core themes:

- why dependency injection matters
- constructor versus field injection
- scopes and lifetimes
- Dagger and Hilt fundamentals
- ViewModel injection
- qualifiers
- assisted injection

Advanced themes:

- component graphs
- custom scopes
- entry points
- compile-time DI versus service location
- Dagger/Hilt versus Koin trade-offs

## Part VII — Networking and communication

Core themes:

- HTTP and HTTPS fundamentals
- Retrofit versus lower-level clients
- OkHttp interceptors and authenticators
- JSON serialization
- bearer tokens and refresh-token flow
- timeouts, retries, and error handling
- certificate pinning
- caching
- WebSockets and streaming choices

Advanced themes:

- idempotency
- TLS and certificate validation at a practical level
- token rotation and concurrent refresh
- resilient networking under poor connectivity
- REST versus GraphQL trade-offs

## Part VIII — Storage and data persistence

Core themes:

- Room versus raw SQLite
- entities, DAOs, and transactions
- migrations
- indexes
- DataStore versus SharedPreferences
- Parcelable versus Serializable
- Paging
- caching and source of truth

Advanced themes:

- multi-table transactions
- schema migration strategy
- database performance diagnosis
- encrypted storage boundaries

## Part IX — Security

Core themes:

- secure PIN and secret storage
- Android Keystore
- encryption at rest
- secure server communication
- certificate pinning trade-offs
- biometric authentication
- exported components and intents
- secure logging
- secret management
- R8 and obfuscation limitations

Advanced themes:

- hardware-backed keys
- attestation and Play Integrity
- root and tamper detection limitations
- threat modelling
- WebView security

## Part X — Performance and reliability

Core themes:

- ANRs
- memory leaks
- startup performance
- jank and frame rendering
- Compose performance
- network and database performance
- battery impact
- StrictMode
- profiling tools

Advanced themes:

- Baseline Profiles
- Macrobenchmark and Microbenchmark
- Perfetto
- memory-pressure behaviour
- release-build measurement
- performance budgets

## Part XI — Testing

Core themes:

- what to unit test
- unit, integration, UI, and end-to-end tests
- test doubles: fake, mock, stub, and spy
- designing for testability
- ViewModel testing
- repository testing
- coroutine and Flow testing
- Compose UI testing
- Espresso
- flaky tests

Advanced themes:

- deterministic virtual time
- contract tests
- screenshot testing
- test pyramid versus testing trophy
- CI test strategy
- avoiding over-mocking

## Part XII — Background processing and offline-first

Core themes:

- WorkManager
- foreground services
- AlarmManager
- JobScheduler
- long-running work
- constraints and retries
- offline-first architecture
- sync queues
- optimistic updates
- conflict handling

Advanced themes:

- idempotent synchronization
- tombstones and deletion propagation
- retry backoff and poison records
- eventual consistency on mobile

## Part XIII — Mobile system design

Core scenarios:

- offline-first notes application
- paginated social feed
- chat application
- media streaming application
- secure banking flow
- image loading and caching
- download manager
- location tracking
- notification architecture

Evaluation themes:

- requirements clarification
- data ownership
- failure modes
- offline behaviour
- security
- observability
- testing
- modularity
- trade-offs

## Part XIV — Behavioral and senior engineering

Core themes:

- technical decisions and trade-offs
- production incidents
- difficult debugging
- mentoring
- code review
- disagreement and conflict
- technical debt
- estimation
- ownership
- cross-functional communication
- leading without authority

## Part XV — Interview process, coding, and project discussion

Core themes:

- explaining a recent Android project and personal ownership
- architecture and technology choices
- debugging and incident stories
- live coding in Kotlin
- data structures and algorithms at the level required by the target role
- code review and refactoring exercises
- communicating assumptions and trade-offs aloud
- take-home assignment strategy

Advanced themes:

- evaluating an unfamiliar codebase
- designing an incremental migration
- defending a decision under changing requirements
- identifying observability, rollout, and failure-recovery needs

## Supporting collections

These are curated after the core modules mature:

- interview traps
- coding exercises
- mock interviews
- project-deep-dive prompts
- company-pattern notes supported by public evidence
- reference appendix

## Current execution order

1. Finalize the Android Platform and Android Runtime question inventory.
2. Research and publish the first 15–25 core questions.
3. Validate the curriculum model against real interview reports.
4. Continue with Kotlin, Coroutines, and Compose.
5. Expand advanced and reference pages only where they support the core curriculum.
