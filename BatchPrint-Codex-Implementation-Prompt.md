# BatchPrint — Codex implementation brief

Paste this entire brief into Codex with the intended GitHub repository open. Treat it as a staged engineering assignment, not a request to generate a finished application in one response.

## 1. Mission and working agreement

Build one coherent, publishable batch-document printing product. Use BatchPrint as a provisional name, without claiming trademark or domain availability. Its purpose is to stop office users opening and printing many documents individually. Users should select PDF/Word documents, arrange them, choose settings and copies, review the batch, and submit it through an authorised Windows printer connection.

The owner wants a serious personal and commercial project, understands Entity Framework, and has deliberately chosen the Microsoft backend ecosystem. Explain material decisions in understandable language. Use only this brief, this repository and information supplied in this project; never import context from unrelated conversations.

Work incrementally: requirements, a technical printing experiment, design, implementation, verification and release preparation. Continue reversible work autonomously. Ask focused questions only for genuinely blocking decisions, credentials, costs, licensing or actions outside the authorised scope. Never claim production readiness because code compiles or a dashboard looks finished.

Keep progress in repository documents so a later session can resume. Do not repeatedly replan completed work. Report implemented behavior, evidence, limitations and the next concrete step. Never manufacture users, testimonials, usage figures, security certifications, test results or physical printing success.

## 2. Product boundaries and committed stack

This is one product, one brand, one account system and one GitHub repository. It contains public marketing pages, account pages, an authenticated printing workspace, an ASP.NET backend and an installed Windows companion. Multiple projects inside the solution are implementation components, not separate products.

Use React, TypeScript and Vite for the frontend; ASP.NET Core Web API, ASP.NET Core Identity and Entity Framework Core for the backend; SQL Server for development and integration tests; Azure SQL Database for the intended hosted environment. Use a supported .NET LTS and compatible packages, verifying versions against official documentation before pinning them. Do not silently replace SQL Server with SQLite or Supabase.

Use a C# Windows companion with a small native status/settings interface. Prefer WPF for that interface. The main workspace remains the browser application; do not create a second elaborate desktop dashboard. The companion handles authorised downloads, conversion, printer discovery and submission. Keep conversion and printing behind interfaces with separately testable implementations.

Use one deployable backend initially, organised into clear modules. Avoid microservices, Kubernetes, event-bus infrastructure, speculative plugin systems and unnecessary abstraction layers. Publish the React assets and API under one origin where practical. Use GitHub for code, issues and CI; Codex remains the single coding assistant.

## 3. Environment audit and repository preparation

First inspect the current repository, AGENTS.md files, existing code, history and uncommitted changes. Preserve user changes. If the earlier BatchPrint prototype exists, assess it rather than regenerating everything. It contains a browser batch planner and disconnected EF/SQLite groundwork, not a complete printing application. Replace its SQLite persistence deliberately; do not imply its existing tests validate SQL Server behavior.

Inventory .NET, Node, Git, browser testing, Docker-compatible runtime and Windows availability. Document unavailable capabilities. Linux can build much of the backend and frontend, but cannot prove Windows printer behavior. Do not substitute simulated printers for hardware acceptance. Use a compatible real SQL Server instance when containers cannot run; otherwise mark those tests blocked.

Create a practical structure: apps/web, src/Api, src/Application, src/Domain, src/Infrastructure, src/WindowsAgent, tests, docs and deployment. Adapt existing names when useful. Pin SDK/runtime requirements, package versions and container images; commit lockfiles and reproducible setup commands. Never commit secrets, real customer documents, database backups or generated dependency directories.

Create concise requirements, architecture decisions, threat model, design brief, test plan, implementation backlog and status documents. Update repository guidance to reflect this agreed architecture, explicitly replacing obsolete SQLite-only or no-account prototype rules while preserving unrelated safeguards. Link requirement IDs to acceptance tests. Keep documentation proportional to decisions; it must support working software, not become an endless planning exercise.

## 4. Agent guidance and external repositories

Do not clone a collection of repositories into the application or assume downloading them teaches permanent skills. Skills provide task instructions; package dependencies provide executable capabilities. Inspect official READMEs, licences, installation procedures and compatibility before selecting either. Record each selected source, purpose, version or commit and permissions in docs/tooling.md.

Relevant sources are openai/skills for optional Codex guidance, github/spec-kit for optional specification templates, and pbakaus/impeccable for optional visual critique. Use only relevant, reviewed guidance. This brief already supplies the project process: do not stack multiple competing orchestration frameworks or let generic templates override its requirements.

Review third-party skill contents and scripts before activation. If available, use cisco-ai-defense/skill-scanner as an additional check; a clean result is not a security guarantee. Start with local/static scanning and do not send private source to external analysis providers without authorisation. Never disable sandboxing, approval controls or security checks because a skill recommends it.

Install testing dependencies through their official package channels instead of cloning their source trees: microsoft/playwright for browser tests, dequelabs/axe-core for accessibility checks, and testcontainers/testcontainers-dotnet for disposable SQL Server integration environments. Use xUnit and frontend behavioral tests. Consult dotnet/AspNetCore.Docs and Microsoft Learn for backend implementation. Verify current installation instructions; do not invent skill paths or commands.

## 5. Competitor references and visual identity

Study these public references: https://www.print-conductor.com/ for batch-printing workflow; https://www.printnode.com/en for printer-client onboarding; https://smallpdf.com/ for approachable document-tool presentation; and https://www.ilovepdf.com/ for clear task organisation. Inspect representative public pages and document what was actually observed. Separate evidence from interpretation. Do not pretend to have tested paid or authenticated interfaces.

The owner's ambition to be dramatically better concerns graphic design, visual identity, frontend craftsmanship and usability. It does not authorise copying competitors' branding, wording, assets or proprietary code, or adding hundreds of unrelated features. Create an original design with recognisable document-product conventions and purposeful details.

Before broad UI implementation, define typography, colour tokens, spacing, grids, radii, elevation, icons, focus states and motion. Start with warm off-white surfaces, deep navy text and a controlled teal or blue accent, then assess actual contrast. Use licensed, preferably self-hosted fonts. Avoid generic gradient-heavy SaaS decoration, repetitive oversized cards, meaningless statistics and fake product screenshots.

Make marketing pages expressive and the workspace calm, compact and task-focused. Build reusable components and inspect real rendered screens. Review at approximately 390, 768 and 1440 CSS pixels, plus long filenames, zoom and touch interaction. Target WCAG 2.2 AA; automated checks supplement keyboard and screen-reader review. Respect reduced-motion settings and avoid colour-only status communication.

## 6. Public website and workspace experience

Public pages should include a clear homepage, genuine product demonstration, supported-platform information, how-it-works steps, early-access information, help, privacy explanation and terms placeholders requiring owner review before publication. Use honest claims and real screenshots only after the corresponding behavior exists. Do not advertise unsupported file formats, offline operation or universal printer compatibility.

The workspace should include a new-batch screen, batch review, job progress, history, printer/device management and account settings. Present one obvious primary action per stage. Support drag-and-drop and accessible file selection, reorder buttons as well as dragging, clear removal, duplicate warnings and per-document copy overrides. Preserve the user's work across appropriate navigations.

Show document count, copy totals and validated page estimates separately. Clearly distinguish copies of each document from collated copies of a complete batch. Define v1 ordering and collation semantics in the requirements; reject unsupported combinations rather than silently approximating them. Actual printer-driver capabilities determine available duplex, colour, tray and paper settings.

Implement empty, loading, validation, disconnected, expired-session, permission-denied, failed and uncertain-outcome states. Errors should explain the next useful action without exposing sensitive details. Responsive layout does not mean mobile printing has been verified; display explicit compatibility guidance and test supported mobile workflows before advertising them.

## 7. Authentication and authorisation

Implement ASP.NET Core Identity backed by EF Core and SQL Server. Provide email/password registration, verification, login, logout, resend verification, password reset and account settings. Add Continue with Google using the official provider and a server-managed callback flow. Google authentication must not request Gmail mailbox access or collect Google passwords.

Use secure HttpOnly browser cookies, suitable SameSite settings, HTTPS and CSRF protection for state-changing requests. Keep credentials and privileged tokens out of browser storage and source code. Persist and protect ASP.NET Data Protection keys appropriately across production restarts and instances. Configure authentication lifetime and invalidation intentionally.

Use Identity's password hashing and token mechanisms rather than custom cryptography. Apply rate limits, lockout protections, safe return-URL validation and non-enumerating recovery responses. Test expired and reused verification/reset links. Provide optional TOTP two-factor enrolment and recovery codes; ensure external-login paths cannot bypass an enabled application MFA requirement. Require reauthentication for sensitive account changes.

Link Google to an existing account only through a verified, authenticated linking process. Do not silently merge accounts solely because an email string matches. Explain when a Google-only account has no local password. Use a real transactional email provider in deployment, with test adapters restricted to development.

Authentication is not sufficient authorisation. Scope batches, documents, devices and download grants to the authenticated owner/workspace on every server operation. Create a personal workspace initially; defer team invitations. Test cross-user access explicitly. The Windows companion uses revocable device credentials, never the user's password or SQL connection string.

## 8. Document data flow and privacy

Use an explicit v1 data flow: browser selection uploads documents temporarily over HTTPS to private object storage; the server records metadata in SQL; an authorised paired Windows companion downloads the required documents and processes them locally. This is not a local-only document product. State that accurately before file selection and in privacy documentation.

Use Azure Blob Storage for intended hosting and a compatible local development substitute. Do not store document binaries in SQL tables, expose public buckets, email files or place customer filenames in general telemetry. Keep original names only where required for the user's workflow; use opaque storage identifiers and server-generated paths.

Set a documented default retention policy: delete uploads after terminal completion plus a short recovery window, with an absolute expiry such as 24 hours from upload. Make these values configurable and visible. Expired or deleted content requires reselection; metadata history does not imply retained documents. Revoke access immediately on deletion and document asynchronous physical cleanup and backup retention separately.

Validate file size, type signatures and supported structure. Start with PDF and DOCX; reject legacy DOC, macro-enabled formats and encrypted documents with clear explanations until separately supported. Treat every parser as an attack surface. Apply limits to expanded archives, pages, memory, CPU and conversion duration. Isolate conversion, disable macros and external resource fetching, and assess malware scanning as part of the production upload path.

## 9. Database and API design

Model only necessary entities: Identity users, workspaces, memberships, registered devices, printer registrations, batches, batch documents, print attempts and minimal security events. Give entities opaque identifiers, ownership fields, UTC timestamps, useful indexes and concurrency controls. Separate source metadata, requested settings, validated settings and submission evidence.

Use EF Core migrations owned by the application. Test migrations against SQL Server and prepare a reviewed production migration process. Avoid automatic destructive migrations at startup. Use separate database credentials/permissions for runtime and schema deployment. In Azure, prefer managed identity where supported; document local secret handling and connection encryption.

Define versioned API contracts, validation rules, pagination, error responses and request-size limits. Enforce idempotency for batch submission and device reports using transactional state transitions and database uniqueness constraints. An idempotency key must be scoped to its owner and operation, not trusted as a global access credential.

Use a database-backed queue initially, with atomic claims and well-defined concurrency. Document state transitions and crash boundaries. Do not rely on in-memory timers as the only durable job system. Store object references rather than document contents in queue messages. Test simultaneous submissions, stale updates and duplicate device responses.

## 10. Windows companion and printer execution

Implement explicit device pairing initiated by an authenticated user. Use expiring, single-use pairing challenges and a clear confirmation naming the computer. Bind credentials to that user's workspace and device. Store device secrets using appropriate Windows protection; support revocation and rotation. Do not expose an unauthenticated local HTTP service or permit arbitrary remote commands.

Prefer outbound authenticated HTTPS polling initially; SignalR can improve responsiveness later if justified. Restrict downloads to authorised document grants, use short-lived access, enforce limits and verify content hashes. Never log signed URLs. Run the companion with ordinary user permissions where possible and define its behavior when the user logs out.

Discover printers through Windows capabilities and return useful names/status without promising every driver supports every option. Perform a PDF printing experiment early, evaluating maintained rendering/printing libraries and redistribution licences. Do not assume Windows can silently print arbitrary PDFs through one universal API. Do not rely on launching file associations as the robust batch engine.

Evaluate DOCX conversion with a representative synthetic corpus. Compare an isolated LibreOffice-based approach with suitable commercial libraries on layout fidelity, fonts, performance, deployment and licensing. Record the decision before integration. Do not purchase a licence or ship evaluation watermarks silently. Keep Word support visibly unavailable until the selected implementation passes acceptance.

Persist a minimal protected device journal around submission; this may be a bounded atomic local journal, not a second application database. Record intent before calling the spooler and correlate acknowledgements afterward. Unresolved journal entries must trigger reconciliation or an uncertain state after restart. Never claim durable database transactions can guarantee exactly-once physical printing.

## 11. Job semantics and recovery

Represent preparation, ready, queued, claimed, submitting, accepted-by-spooler, failed, cancelled and uncertain states with documented transitions. Physical completion is a separate observation available only when the printer/driver supplies credible evidence. The interface must not translate accepted-by-spooler into physically printed.

Keep durable per-document attempt records. A retryable download error is different from a lost acknowledgement after spool submission. Before submission, expired claims can be recovered under explicit rules; after submission may have begun, do not automatically reassign or repeat the job. A user-confirmed reprint creates a new attempt and explains duplication risk.

Cancellation stops unsubmitted work. Attempt spool cancellation where supported, but explain that pages already printed cannot be recalled. Define batch behavior when one document fails: pause or continue according to an explicit user setting, with a safe documented default. Avoid silently skipping files while reporting batch success.

Test internet loss, companion restart, API restart, printer offline, paper mismatch, conversion timeout and duplicate button clicks. Retain enough evidence to explain outcomes without retaining unnecessary document contents. Support a diagnostic export with redaction and user consent, not unrestricted document or secret collection.

## 12. TDD and verification strategy

For domain rules and defect fixes, write a meaningful failing test first, implement the smallest correct behavior, then refactor. Preserve evidence of test commands and outcomes. Do not generate superficial tests that merely mirror implementation, mock the entire system or assert that buttons exist. Never weaken assertions to hide failures.

Use xUnit for domain/backend tests and real SQL Server integration tests, preferably through Testcontainers when supported. Verify migrations, constraints, ownership filtering, idempotency, queue claims and concurrent updates. Do not use SQLite or EF's in-memory provider as proof of SQL Server correctness. Keep synthetic fixtures deterministic and legally redistributable.

Use frontend behavioral tests and Playwright for registration, login, protected navigation, batch preparation, validation, device states and recovery. Use a clearly marked test device adapter for CI, unavailable in production. Cover at least two separate users attempting cross-account access. Test CSRF protections, unsafe redirect handling, rate limits and cookie configuration.

Run axe-based accessibility checks and manually inspect keyboard focus, dialogs, errors, contrast, zoom and responsive layouts. Check browser console errors and define reasonable performance budgets. Compare screenshots for important states; a visually polished empty page alone is insufficient evidence.

Create a Windows hardware acceptance matrix with representative printers/drivers and synthetic PDF/DOCX fixtures. Verify order, copies, page boundaries, duplex and cancellation. Record actual output and operator observations. Hardware tests that cannot run remain pending; never label a mock-based suite as physical-print verification.

## 13. Delivery milestones and release gates

Milestone A: inspect the repository, produce concise requirements and architecture decisions, establish reproducible builds, and execute the smallest real Windows PDF-print experiment. If Windows is unavailable, implement the adapter contract and bounded independent work, but record the printing experiment as blocked and do not claim end-to-end feasibility verified.

Milestone B: establish SQL Server migrations, account ownership, email/Google authentication and secure device pairing. Build the public shell and account screens using the design system. Include a development email setup and concrete instructions for supplying deployment credentials securely. No fake working Google button.

Milestone C: implement private document upload, validation, queueing, companion download, PDF submission and honest status reporting as one vertical slice. Demonstrate browser-to-printer behavior on actual Windows hardware. Then integrate verified DOCX conversion and supported batch settings. Protect already-working behavior with regression tests.

Milestone D: polish the website, workspace, responsive layouts, account settings, recovery flows and help. Run security, dependency, accessibility and performance checks. Resolve high-impact findings, document accepted limitations and prepare an installer with a defined signing/update strategy.

Milestone E: prepare staging deployment and a small pilot release. Use Azure hosting compatible with ASP.NET Core, Azure SQL and private Blob Storage. Produce infrastructure configuration and cost assumptions; do not provision paid resources, purchase services, accept contracts or publish customer data without explicit authorisation. Lack of credentials must not prevent local implementation or a complete deployment runbook.

## 14. Operations and definition of done

Provide GitHub CI for backend/frontend builds, tests, SQL Server integration, dependency auditing and secret scanning. Use least-privilege workflow permissions, reviewed action versions and protected deployment environments. Keep production secrets outside repository files and browser bundles. Create health checks, structured redacted logs, retention cleanup and actionable operational alerts.

Document backup/restore, application rollback, database forward-fix strategy, account deletion and device revocation. Test restore procedures in a safe environment. Verify that expired files are cleaned up, failed cleanup is retried and logs do not contain document content. Provide installation, update, uninstall and troubleshooting instructions for the Windows companion.

Release readiness requires working email delivery, configured Google login, enforced ownership checks, verified storage access, tested migrations, a verified signed installer, hardware results and reviewed privacy wording. If any gate is missing, label the result development, staging or private alpha as appropriate; do not call it production-ready.

Leave pricing experimental: a clearly described pilot is sufficient. Do not add payment collection, advertising SDKs, tracking pixels, AI chat, OCR or unrelated PDF utilities to this version. Commercial expansion follows observed usefulness, reliability and support costs.

Start now with the repository audit and first milestone. Implement rather than stopping after a plan. At each checkpoint report changed files, commands executed, tests passed/failed/blocked, decisions requiring the owner and the next action. Maintain a current status file with exact continuation instructions. The final handover must include runnable source, configuration examples without secrets, test evidence, deployment instructions and an honest list of unresolved release gates.
