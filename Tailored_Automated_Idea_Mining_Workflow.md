# Tailored Automated Idea-Mining Workflow

## 1. Purpose

This workflow defines a deterministic, local-first system for collecting, reviewing, validating, comparing, scoring, ranking, and maintaining evidence-backed software and standardized-service opportunities.

Its intended outcomes are:

- A continuously updated ranked backlog.
- A strict separation between early **Leads** and **Qualified Opportunities**.
- A ranked set of primary standalone opportunities.
- A secondary **Portfolio Reserve** for complementary products and services.
- Public professional contact routes, when legitimately available.
- Controlled outreach that never bypasses human approval.
- An honest result of zero qualified opportunities whenever the evidence does not justify promotion.

The system automates repeatable mechanics. It does not conduct unsupervised semantic judgment, invent evidence, lower qualification standards, or replace required human decisions.

## 2. Scope and Inherited Controls

### 2.1 Target-Market Priority

Each scheduled run follows this repeating weekly priority rotation:

1. Solopreneurs, solo founders, solo developers, indie developers, small development teams, and SMBs.
2. Office-based business professionals, including remote equivalents.
3. Residential and commercial construction companies, general contractors, and subcontractors.
4. Small video-game studios.

The operator selects one narrow segment within the scheduled priority before approving a run. On-demand runs may use any approved segment and do not alter the scheduled rotation.

Favor markets where competency, usefulness, deliverable quality, demonstrated results, and reliability matter more than founder reputation, institutional pedigree, or background screening.

Exclude:

- Public and private education
- Finance
- Legal services
- Government
- Licensing-dependent markets
- Clearance-dependent markets
- Reputation- or background-dependent markets
- Markets with comparable trust or regulatory barriers

### 2.2 Qualifying Product and Service Forms

Eligible responses include:

- Micro-SaaS
- Windows applications
- Linux applications
- Browser extensions
- Android applications
- Focused web applications
- Software-supported productized services
- Standalone standardized services
- Secondary portfolio products

A software product may support any approved platform subset. Supporting every approved platform is not required.

Do not officially target or support macOS or iOS. Incidental web access is acceptable. Android-only and mobile-first opportunities remain eligible but receive the lowest platform tie-break priority.

### 2.3 Architecture and Data Principles

Every qualifying opportunity must support:

- Maximum practical user control over data
- Data export or portability
- Transparent data handling
- Cloud functionality that is explicitly user-opt-in
- No sale of user data

Full local-first operation is strongly preferred when technically practical. Hybrid architectures may qualify when the user deliberately enables cloud functions. Open-source publication is optional.

### 2.4 Revenue and Customer Interaction

Allowed revenue models include:

- Subscriptions
- One-time purchases
- Paid upgrades
- Paid add-ons
- Paid pilots
- Productized-service fees
- Standardized-service fees
- Privacy-respecting advertising

Advertising-dependent opportunities receive the lowest revenue-model priority unless exceptionally beneficial. Selling user data remains prohibited.

Allowed customer interaction is:

- Self-service
- Low-touch sales
- Low-touch onboarding
- Low-touch support
- Standardized hands-on delivery for an approved service

Reject opportunities requiring:

- Constant support
- Extensive customization
- High-touch account management at scale
- A large sales operation
- Employees or contractors

### 2.5 Founder Feasibility

Every qualifying opportunity must be reasonably capable of:

- Reaching an initial usable version in roughly three months
- Being built and operated by one founder
- Using AI-assisted development during later product building
- Using the founder’s current computer, local models, and existing subscriptions
- Starting without upfront or pre-revenue spending

Revenue may later fund proportionate hosting, payment processing, storage, distribution, and operating costs.

### 2.6 Geographic and Language Scope

Count only evidence reasonably applicable to:

- United States customers
- English-language products, services, reviews, discussions, and outreach

Location-ambiguous evidence may remain contextual or support a Lead when the workflow clearly applies to the United States. It may not satisfy final qualification unless other context supports U.S. applicability.

## 3. Automation Boundary

### 3.1 Deterministic Responsibilities

The system may perform the following without interpretive AI:

- Create scheduled and on-demand run records.
- Rotate scheduled runs through priorities 1, 2, 3, and 4.
- Generate queries from approved templates and operator-supplied terms.
- Execute only approved source plans through permitted adapters.
- Capture candidate text and structured metadata.
- Apply transparent keyword, exact-phrase, regular-expression, and field-validation rules.
- Calculate cutoff dates and recency bands.
- Generate immutable record identifiers.
- Detect exact identifiers, URLs, text hashes, and previously approved duplicates.
- Count approved users, source types, recent evidence, and commercial signals.
- Enforce required gates and promotion thresholds.
- Calculate weighted scores, bands, rankings, and tie-breaks.
- Maintain record states, queues, follow-up dates, suppression states, and retention deadlines.
- Synchronize authorized fields with Google Sheets.
- Create notifications, checkpoints, backups, and audit records.
- Populate approved outreach templates with verified fields.
- Send a business email only after a current, message-specific human approval.

### 3.2 Human-Approval Responsibilities

Human approval is mandatory for:

- The narrow segment and one to three workflows for each run
- Planned sources, query terms, query preview, and coverage bounds
- Whether candidate text is credible, first-hand evidence
- The exact excerpt that becomes the evidence record
- U.S. applicability when it is not explicit
- Workflow, problem, workaround, consequence, and commercial-signal meaning
- Ambiguous duplicate-person, cross-platform identity, or shared-incident decisions
- Pain-cluster membership and the required four-of-five element match
- Counterevidence interpretation and current-product status
- Whether a problem is resolved, partially resolved, underserved, unserved, served, or unclear
- Judgment-based pass/fail gates
- Every zero-to-five scoring rating
- Public-contact appropriateness
- Every initial outreach message
- Every follow-up message
- Every browser-based outbound submission
- Manual overrides, corrections, and reopening archived records

### 3.3 Deferred AI-Enhancement Candidates

The following may be considered by Instance 3 but are not part of this deterministic design:

- Interpreting paraphrased complaints
- Extracting meaning from unstructured prose
- Suggesting semantic pain clusters
- Suggesting non-exact duplicates
- Summarizing counterevidence
- Proposing gate decisions or score ratings
- Identifying implicit commercial signals
- Drafting natural-language personalization
- Detecting nuanced conflicts across sources

Until an AI-assisted design is separately confirmed, these tasks remain human decisions or transparent deterministic approximations.

## 4. High-Level Architecture

The system is a local Windows 11 application implemented in Python and packaged for normal desktop use.

### 4.1 Components

1. **Local Operator Dashboard**
   - Runs only on the local computer.
   - Binds to the loopback interface rather than a public network interface.
   - Provides run setup, review queues, gates, scoring, outreach approval, errors, and maintenance controls.

2. **Scheduler and Run Orchestrator**
   - Integrates with Windows Task Scheduler.
   - Creates weekly and on-demand runs.
   - Enforces pending approval, single-run execution, priority rotation, checkpoints, and stopping rules.

3. **Configuration and Rule Registry**
   - Stores approved segments, workflow terms, query templates, keyword patterns, source-type mappings, thresholds, formulas, state rules, and version history.
   - Makes every rule change auditable.

4. **Source-Adapter Layer**
   - Provides separate, versioned adapters for approved source families.
   - Uses free official access first, permitted browser automation second, and manual import last.
   - Isolates failures so one source cannot corrupt the remaining run.

5. **Dedicated Edge Automation Profile**
   - Isolates automation cookies, sessions, history, and settings from ordinary browsing.
   - Uses user-performed login.
   - Does not expose passwords to the workflow.

6. **Collection Queue**
   - Executes one source interaction at a time.
   - Applies per-source coverage limits and pacing.
   - Persists progress after each completed item or batch.

7. **Candidate and Evidence Review Engine**
   - Stores candidate captures separately from approved evidence.
   - Applies transparent matching and validation rules.
   - Prevents unreviewed material from affecting qualification.

8. **Qualification and Ranking Engine**
   - Enforces evidence thresholds and pass/fail gates.
   - Calculates scores only after all gates pass.
   - Applies priority bands and tie-breakers exactly.

9. **Outreach State Machine**
   - Creates deterministic message drafts.
   - Enforces per-message approval, one-channel limits, one follow-up, opt-outs, and cancellation rules.
   - Separates approved email sending from manually submitted browser channels.

10. **SQLite Operational Database**
    - Is the authoritative data store.
    - Owns queues, state transitions, audit history, synchronization versions, and recoverable checkpoints.

11. **Local Evidence File Store**
    - Holds permitted screenshots, snippets, content hashes, and private reply content.
    - Applies retention and access rules.

12. **Google Sheets Synchronizer**
    - Publishes the human-facing backlog, reports, mobile review queues, and designated approval fields.
    - Accepts only validated edits from authorized columns.

13. **Credential Broker**
    - Retrieves tokens from Windows Credential Manager.
    - Keeps credentials out of source code, configuration files, Sheets, and logs.

14. **Audit, Backup, and Recovery Service**
    - Maintains append-only events, run checkpoints, before-and-after values, and rolling backups.

15. **Notification Service**
    - Sends Windows and email notifications for approvals, intervention, failures, completion, and due outreach.

## 5. Authoritative Data and Synchronization

### 5.1 Authority Rule

SQLite is authoritative when local records and Google Sheets disagree.

Google Sheets is:

- The synchronized backlog
- The reporting surface
- A mobile review surface
- A controlled human-input and approval surface

Google Sheets is not permitted to overwrite protected system fields.

### 5.2 Permitted Sheet Inputs

Only explicitly designated fields may be edited in Sheets, such as:

- Review decision
- Human classification
- Human notes
- Gate decision
- Gate rationale
- Zero-to-five score rating
- Outreach approval
- Response status for manually monitored channels
- Override request and reason

Protected fields include:

- Immutable IDs
- Source URLs and captured provenance
- Source-type mappings
- Calculated dates
- Counts
- Formulas
- Scores
- Rankings
- State-transition history
- Audit metadata
- Rule versions
- Suppression state

### 5.3 Safe Inbound Synchronization

Every editable Sheet row includes:

- Record ID
- Record version
- Allowed action
- Action value
- Optional reason
- Approval timestamp

The synchronizer:

1. Reads only allowed columns.
2. Confirms that the record version is current.
3. Validates the action against the record’s current state.
4. Rejects stale, malformed, or unauthorized edits.
5. Writes an audit event.
6. Applies the accepted change to SQLite.
7. Increments the record version.
8. Refreshes the Sheet projection.

A stale or conflicting approval pauses the action and creates a review notification.

### 5.4 Sheet Availability Failures

If Google Sheets is unavailable:

- Local collection and review may continue through the dashboard.
- Outbound synchronization is queued.
- Mobile approvals are unavailable.
- No queued Sheet approval is assumed.
- Reconnection resumes idempotently from the last confirmed synchronization version.

## 6. Google Sheets Workbook

Use one private workbook named:

`Automated Idea-Mining Backlog`

The workbook uses these core tabs:

1. **Run Control**
2. **Source and Query Log**
3. **Evidence**
4. **Leads**
5. **Qualified Opportunities**
6. **Rejected and Archived**
7. **Outreach**
8. **Portfolio Reserve**

Add these automation-support tabs:

9. **Review Queue**
10. **Approvals**
11. **Source Adapter Status**
12. **Rule Versions**
13. **Audit Summary**

The canonical workflow fields remain represented. Automation-support fields include:

- Record version
- Sync status
- Review task ID
- Approval state
- Approval timestamp
- Rule version
- Last system update
- Last human update
- Conflict status
- Adapter health
- Failure code
- Recovery action

The workbook must remain private to the operator’s Google account unless the operator explicitly changes access.

## 7. Canonical Data Model

### 7.1 Identity Strategy

Each record receives:

- An immutable internal UUID
- A readable workflow ID
- Created and modified timestamps
- Creator or actor
- Current version
- Current state
- Governing rule version

Readable IDs include:

- `RUN-[DATE]-[SEQUENCE]`
- `QRY-[RUN]-[SEQUENCE]`
- `CAP-[RUN]-[SEQUENCE]`
- `EV-[SEGMENT]-[SEQUENCE]`
- `PC-[SEGMENT CODE]-[THREE-DIGIT NUMBER]`
- `LEAD-[SEGMENT]-[SEQUENCE]`
- `OPP-[SEGMENT]-[SEQUENCE]`
- `OUT-[SEQUENCE]`
- `PORT-[SEQUENCE]`

IDs are never reused after rejection, deletion, or archival.

### 7.2 Core Records

#### Run

Stores:

- Scheduled or on-demand origin
- Scheduled priority
- Selected narrow segment
- Selected role
- One to three workflows
- U.S. applicability rule
- Run date
- 12-month and 36-month cutoffs
- Approved sources and source types
- Coverage bounds
- Approval record
- Current state
- Stopping-condition results
- Coverage limitations
- Final quality status

#### Source Adapter

Stores:

- Source family
- Source type
- Adapter version
- Confirmed access method
- Authentication requirement
- Terms or access-review date
- Pacing configuration
- Supported fields
- Health state
- Last successful execution
- Current fallback

#### Query Family and Query Execution

Stores:

- Exact approved template
- Substituted terms
- Exact resulting query
- Source
- Source type
- Date window
- Result or page bound
- Approval
- Execution attempts
- Results reviewed
- New clusters created
- Existing clusters strengthened
- Counterevidence found
- No-new-theme sequence
- Access limitations

#### Candidate Capture

Stores unapproved:

- Source identifier
- Source URL
- Captured public text
- Public author or account label
- Publication date
- Product version or platform context when shown
- Matched deterministic rule
- Capture timestamp
- Content hash
- Local permitted snapshot reference
- Review state

A Candidate Capture never counts toward evidence thresholds.

#### Evidence Item

Stores:

- Evidence ID
- Run ID
- Pain Cluster ID
- Source type and source name
- Source URL
- Publication date and recency band
- Public author or account label
- User or customer context
- U.S. applicability
- Exact public excerpt
- Workflow or job
- Pain category
- Problem
- Workaround
- Consequence
- Commercial-signal type and details
- Product, competitor, or platform
- First-hand status
- Independence status
- Duplicate status
- Credibility status
- Threshold eligibility
- Snapshot reference
- Contact availability and permitted route
- Counterevidence relationship
- Human approver and approval time

#### Public Participant

Stores only public, necessary identity information:

- Source-local account label
- Source-local profile URL
- Explicit public professional link, if present
- Approved contact route
- Pain-cluster participation
- Suppression status

Cross-platform records are linked only when:

- The person explicitly publishes the link, or
- The operator approves clear public linkage.

The system never attempts deanonymization.

#### Pain Cluster

Stores:

- Target user type
- Job or desired outcome
- Workflow stage
- Failure or constraint
- Consequence
- Workaround
- Approved member evidence
- Counterevidence
- Independent-user count
- Source-type count
- Recent-evidence count
- Commercial-signal count
- Validation gaps
- Human clustering decisions

#### Lead

Stores:

- Specific user and workflow
- Clear problem statement
- At least one credible first-hand item
- Plausible consequence
- Missing evidence
- Next validation action
- Possible product or service form
- Platform and data-control fit
- Standalone or portfolio hypothesis
- Current status

#### Competitor Check

Stores:

- Direct competitors
- Adjacent tools
- Manual and spreadsheet workarounds
- Productized services
- Free or open-source alternatives
- Current official facts
- Supporting URLs
- Verification dates
- Human gap decision
- Unresolved risks

#### Gate Decision

Stores:

- Gate number and name
- Pass or fail
- Human or deterministic owner
- Supporting records
- Rationale
- Rule version
- Approver
- Timestamp
- Superseded decision, if changed

#### Scorecard

Stores:

- Each zero-to-five human rating
- Maximum points
- Calculated points
- Four category totals
- Total score
- Priority band
- Applied tie-break values
- Rating evidence and rationale
- Score rule version

#### Qualified Opportunity

Stores:

- Opportunity label
- Target segment
- Problem statement
- Focused outcome
- Product or service form
- Approved platform
- Standalone or portfolio classification
- Revenue options
- Local-first or hybrid fit
- Gate result
- Score and band
- Rank
- Key evidence and counterevidence
- Competitor-check summary
- Main unresolved risk
- Next validation step

#### Contact Route

Stores:

- Public professional channel
- Exact public route
- Contact-source URL
- Appropriateness approval
- Last relevance date
- Retention deadline
- Suppression state

#### Outreach Record

Stores:

- Evidence and Pain Cluster links
- Contact label and one selected channel
- Outreach stage
- Message version and content hash
- Personalized public-problem reference
- Approval
- Initial-contact date
- Follow-up due date
- Follow-up date
- Response state
- Private response reference
- Factual response summary
- Commercial signal
- Consent or quotation status
- Opt-out state
- Next permitted action

#### Audit Event

Stores:

- Event ID
- Timestamp
- Actor
- Component
- Action
- Record ID
- Previous value
- New value
- Rule or adapter version
- Input provenance
- Reason
- Correlation or run ID

Audit events must not contain credentials or full private replies.

## 8. Record States and State Transitions

### 8.1 Run States

`Draft → Pending Approval → Queued → Collecting → Awaiting Review → Qualification Review → Closing → Completed`

Alternate states:

- `Paused—Human Action`
- `Incomplete`
- `Failed`
- `Cancelled`

No state transition may skip a required approval or quality checkpoint.

### 8.2 Candidate States

`Captured → Pending Review → Count | Context Only | Duplicate | Rejected`

Only `Count` creates or updates an Evidence Item eligible for thresholds.

### 8.3 Lead States

`Active → Validation Needed → Near Threshold → Ready for Qualification → Promoted`

Alternate states:

- `Rejected`
- `Archived`
- `Portfolio Reserve`

Promotion creates a Qualified Opportunity only after every gate passes and scoring completes.

### 8.4 Opportunity States

- `Gate Review`
- `Scoring`
- `Priority A`
- `Priority B`
- `Priority C`
- `Qualified Hold`
- `Rejected`
- `Archived`

### 8.5 Outreach States

`Eligible → Drafted → Pending Approval → Approved → Sent | Awaiting Manual Send → Awaiting Response`

Possible next states:

- `Responded`
- `Follow-Up Due`
- `Follow-Up Drafted`
- `Follow-Up Pending Approval`
- `Follow-Up Sent`
- `Closed—No Response`
- `Closed—Rejected`
- `Closed—Opted Out`
- `Closed—Delivery Failure`
- `Closed—Platform Prohibited`

No person may have more than one active contact channel for the same research purpose.

## 9. Scheduling and Run Control

### 9.1 Weekly Schedule

Windows Task Scheduler creates a scheduled run every Monday at 10:00 a.m. Eastern Time.

The continuous rotation is:

- Week 1: Priority 1
- Week 2: Priority 2
- Week 3: Priority 3
- Week 4: Priority 4
- Week 5: Restart at Priority 1

The rotation advances when the scheduled run record is created. An on-demand run never changes the scheduled rotation.

### 9.2 Missed Schedule

If the computer is off at the scheduled time:

- Windows Task Scheduler starts the scheduler at the next startup.
- The system creates the missed run with its original scheduled timestamp.
- The run remains `Pending Approval`.
- The priority is not skipped.

### 9.3 Overlapping Runs

Only one run may collect at a time.

If a previous run is unfinished:

- The next scheduled run is still created.
- It enters the queue with its assigned priority.
- It does not execute concurrently.
- The operator receives an overdue-run notification.
- The operator may complete, cancel, or explicitly reorder queued runs.
- Reordering is audited and does not silently rewrite the weekly rotation history.

### 9.4 Run Approval Package

Before collection, the operator must approve:

- Scheduled priority
- Narrow segment
- Selected role
- One to three workflows
- U.S. applicability rule
- Planned source types
- Specific sources
- Query terms
- Generated query preview
- Recent and older date windows
- Per-query or per-source coverage bounds
- Authentication requirements
- Manual fallbacks

Changing any approved field invalidates the existing run approval.

## 10. Query Generation

### 10.1 Inputs

The operator selects:

- Three to six approved pain phrases
- Two to four workflow terms
- Relevant product or competitor names
- Relevant platform terms
- One or more approved communities or domains

### 10.2 Deterministic Generation

The Query Generator:

1. Selects only templates approved for the scheduled segment and source.
2. Replaces every required template field with an approved term.
3. Rejects unresolved placeholders.
4. Applies the run’s date window.
5. Removes exact duplicate queries.
6. Labels each query with its source type and query family.
7. Displays the exact queries and coverage bounds for approval.

The generator does not invent synonyms, communities, competitors, or workflows.

### 10.3 Query Library

The following seed library is versioned and operator-editable. Every change creates a new rule version. Historical runs continue to reference the version they used.

#### 10.3.1 Universal Pain and Workaround Phrases

- `"manual entry"`
- `"copy and paste"`
- `"re-enter"`
- `"export to Excel"`
- `"export to Sheets"`
- `"we use a spreadsheet"`
- `"had to build a workaround"`
- `"had to use another tool"`
- `"spending hours"`
- `"takes forever"`
- `"error prone"`
- `"keeps breaking"`
- `"wish it had"`
- `"is there a tool that"`
- `"does anyone know software"`
- `"how do you handle"`

#### 10.3.2 Pricing and Complexity Phrases

- `"too expensive for one person"`
- `"too expensive for a small team"`
- `"overkill for our team"`
- `"too complex for what we need"`
- `"we only use"`
- `"paying for features we do not use"`
- `"forced upgrade"`
- `"seat minimum"`
- `"looking for an alternative"`
- `"tired of paying for"`

#### 10.3.3 Integration and Handoff Phrases

- `"doesn't integrate with"`
- `"doesn't connect with"`
- `"no integration"`
- `"sync is unreliable"`
- `"import failed"`
- `"export is limited"`
- `"duplicate entry"`
- `"switch between tools"`
- `"move data manually"`
- `"field to office"`
- `"handoff"`

#### 10.3.4 Platform and Data-Control Phrases

- `"no Linux support"`
- `"doesn't work on Linux"`
- `"Windows only"`
- `"doesn't work on Android"`
- `"mobile app is unusable"`
- `"cloud only"`
- `"need offline"`
- `"works offline"`
- `"self-hosted alternative"`
- `"data export"`
- `"vendor lock-in"`
- `"own my data"`
- `"privacy"`
- `"telemetry"`

#### 10.3.5 Targeted Workflow Terms

**Solopreneurs, developers, and small teams**

- `client intake`
- `issue triage`
- `release notes`
- `documentation`
- `deployment`
- `environment setup`
- `project handoff`
- `local development`
- `browser workflow`
- `small-team tooling`

**Business professionals**

- `approval workflow`
- `report assembly`
- `file version`
- `form responses`
- `recurring report`
- `data reconciliation`
- `document handoff`
- `meeting actions`
- `operations dashboard`
- `client onboarding`

**Construction**

- `daily log`
- `punch list`
- `change order`
- `field report`
- `jobsite photos`
- `subcontractor coordination`
- `material tracking`
- `document version`
- `field to office`
- `offline jobsite`

**Small video-game studios**

- `asset pipeline`
- `build distribution`
- `bug triage`
- `playtest feedback`
- `localization`
- `version control`
- `release checklist`
- `production tracking`
- `engine integration`
- `creative handoff`

### 10.4 Query Templates

Every bracketed field must resolve to an approved value before a query can enter the run.

#### 10.4.1 Universal Reddit and Public-Forum Templates

```text
site:reddit.com/r/[SUBREDDIT] "[PAIN_PHRASE]" "[WORKFLOW_TERM]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SUBREDDIT] "is there a tool that" "[WORKFLOW_TERM]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SUBREDDIT] "how do you handle" "[WORKFLOW_TERM]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SUBREDDIT] "spending hours" "[WORKFLOW_TERM]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SUBREDDIT] "we use a spreadsheet" "[WORKFLOW_TERM]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SUBREDDIT] "too expensive for" "[USER_TYPE]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SUBREDDIT] "overkill for our team" "[TOOL_CATEGORY]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SUBREDDIT] "doesn't integrate with" "[TOOL_OR_WORKFLOW]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SUBREDDIT] "looking for an alternative" "[COMPETITOR]" after:[12_MONTH_CUTOFF]
site:[APPROVED_FORUM_DOMAIN] "[PAIN_PHRASE]" "[WORKFLOW_TERM]" after:[12_MONTH_CUTOFF]
```

Older-window forms are enabled only after recent recurrence is present:

```text
site:reddit.com/r/[SUBREDDIT] "[PAIN_PHRASE]" "[WORKFLOW_TERM]" after:[36_MONTH_CUTOFF] before:[12_MONTH_CUTOFF]
site:[APPROVED_FORUM_DOMAIN] "[PAIN_PHRASE]" "[WORKFLOW_TERM]" after:[36_MONTH_CUTOFF] before:[12_MONTH_CUTOFF]
```

#### 10.4.2 Solopreneur, Developer, and Small-Team Templates

```text
site:reddit.com/r/[SOLO_OR_DEV_SUBREDDIT] "too expensive for one person" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SOLO_OR_DEV_SUBREDDIT] "manual" "client intake" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SOLO_OR_DEV_SUBREDDIT] "spending hours" "issue triage" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SOLO_OR_DEV_SUBREDDIT] "workaround" "release notes" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SOLO_OR_DEV_SUBREDDIT] "doesn't work on Linux" "[TOOL_CATEGORY]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[SOLO_OR_DEV_SUBREDDIT] "we only use" "features" "[COMPETITOR]" after:[12_MONTH_CUTOFF]
site:stackoverflow.com/questions "[WORKFLOW_TERM]" "manual workaround" after:[12_MONTH_CUTOFF]
site:github.com "[WORKFLOW_TERM]" "manual workaround" "issue" after:[12_MONTH_CUTOFF]
```

#### 10.4.3 Business-Professional Templates

```text
site:reddit.com/r/[ROLE_SUBREDDIT] "spending hours" "[OFFICE_TASK]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[ROLE_SUBREDDIT] "manual entry" "[OFFICE_TASK]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[ROLE_SUBREDDIT] "we use a spreadsheet" "[OFFICE_TASK]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[ROLE_SUBREDDIT] "doesn't integrate with" "[BUSINESS_TOOL]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[ROLE_SUBREDDIT] "too complex for what we need" "[BUSINESS_TOOL]" after:[12_MONTH_CUTOFF]
site:[APPROVED_PROFESSIONAL_FORUM] "copy and paste" "[OFFICE_TASK]" after:[12_MONTH_CUTOFF]
site:[APPROVED_PROFESSIONAL_FORUM] "looking for an alternative" "[COMPETITOR]" after:[12_MONTH_CUTOFF]
```

#### 10.4.4 Construction Templates

```text
site:reddit.com/r/[CONSTRUCTION_SUBREDDIT] "manual" "daily log" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[CONSTRUCTION_SUBREDDIT] "spreadsheet" "punch list" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[CONSTRUCTION_SUBREDDIT] "spending hours" "field report" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[CONSTRUCTION_SUBREDDIT] "field to office" "workaround" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[CONSTRUCTION_SUBREDDIT] "doesn't integrate with" "[CONSTRUCTION_TOOL]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[CONSTRUCTION_SUBREDDIT] "too expensive for a small team" "[CONSTRUCTION_TOOL]" after:[12_MONTH_CUTOFF]
site:[APPROVED_CONSTRUCTION_FORUM] "manual entry" "[CONSTRUCTION_WORKFLOW]" after:[12_MONTH_CUTOFF]
site:[APPROVED_CONSTRUCTION_FORUM] "looking for an alternative" "[CONSTRUCTION_COMPETITOR]" after:[12_MONTH_CUTOFF]
```

#### 10.4.5 Small-Game-Studio Templates

```text
site:reddit.com/r/[GAMEDEV_SUBREDDIT] "manual" "asset pipeline" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[GAMEDEV_SUBREDDIT] "spending hours" "build distribution" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[GAMEDEV_SUBREDDIT] "workaround" "playtest feedback" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[GAMEDEV_SUBREDDIT] "too expensive for a small team" "[GAMEDEV_TOOL]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[GAMEDEV_SUBREDDIT] "doesn't integrate with" "[ENGINE_OR_TOOL]" after:[12_MONTH_CUTOFF]
site:reddit.com/r/[GAMEDEV_SUBREDDIT] "we use a spreadsheet" "[STUDIO_WORKFLOW]" after:[12_MONTH_CUTOFF]
site:github.com "[ENGINE_OR_TOOL]" "[STUDIO_WORKFLOW]" "workaround" "issue" after:[12_MONTH_CUTOFF]
site:[APPROVED_GAMEDEV_FORUM] "looking for an alternative" "[GAMEDEV_COMPETITOR]" after:[12_MONTH_CUTOFF]
```

#### 10.4.6 Structured Review-Site Templates

```text
site:g2.com/products "[TOOL_CATEGORY]" reviews
site:capterra.com "[TOOL_CATEGORY]" reviews
site:getapp.com "[TOOL_CATEGORY]" reviews
site:softwareadvice.com "[TOOL_CATEGORY]" reviews
```

Permitted page-local candidate terms:

```text
manual
workaround
spreadsheet
export
integration
overkill
expensive
complex
offline
Linux
Android
data
```

#### 10.4.7 Application and Extension Marketplace Templates

```text
site:play.google.com/store/apps "[TOOL_CATEGORY]" "[PAIN_PHRASE]"
site:chromewebstore.google.com "[TOOL_CATEGORY]" "[PAIN_PHRASE]"
site:microsoftedge.microsoft.com/addons "[TOOL_CATEGORY]" "[PAIN_PHRASE]"
site:apps.microsoft.com "[TOOL_CATEGORY]" "[PAIN_PHRASE]"
```

#### 10.4.8 Pricing and Suite-Tax Templates

```text
"[COMPETITOR]" "too expensive for one person"
"[COMPETITOR]" "too expensive for a small team"
"[COMPETITOR]" "overkill for our team"
"[COMPETITOR]" "we only use" "features"
"[COMPETITOR]" "paying for features"
"[COMPETITOR]" "seat minimum"
"[COMPETITOR]" "forced upgrade"
"alternative to [COMPETITOR]" "[USER_TYPE]"
```

#### 10.4.9 Neutral and Opposing Templates

```text
"[TOOL]" fixed "[PROBLEM]"
"[TOOL]" now supports "[FEATURE]"
"[WORKFLOW]" works well "[TOOL]"
"best way to [WORKFLOW]" "[USER_TYPE]"
```

## 11. Source-Adapter Strategy

### 11.1 Access Hierarchy

For every source:

1. Use a free, official API, feed, or export only when current availability, permissions, and limits have been verified.
2. Otherwise use permitted visible-browser automation through the dedicated Edge profile.
3. Otherwise create a manual-collection task with the exact source, query, and required fields.

No source capability is assumed merely because it has existed previously.

### 11.2 Adapter Access Manifest

Before an adapter may run, its manifest must record:

- Source family
- Source type
- Current approved access method
- Date the access method was verified
- Authentication requirement
- Permitted fields
- Published limits or operator-approved conservative limits
- Browser or API mode
- Manual fallback
- Adapter version
- Health-test status

An expired or failed manifest prevents automated access until reviewed.

### 11.3 Approved Source Families and Fallbacks

| Source family | Source type | Preferred access | Permitted fallback |
|---|---|---|---|
| G2, Capterra, GetApp, Software Advice | Structured software-review platforms | Verified free official access, if available and allowed | Permitted visible browser collection; otherwise manual capture |
| Reddit and relevant public professional communities | Public communities and professional forums | Verified official access, if available and allowed | Permitted visible browser collection; otherwise manual capture |
| Google Play, Chrome Web Store, Edge Add-ons, Microsoft Store | Application and extension marketplaces | Verified official access or export, if available and allowed | Permitted visible browser collection; otherwise manual capture |
| GitHub Issues or Discussions, Stack Overflow | Technical issue and question sources | Verified official access, if available and allowed | Permitted visible browser collection; otherwise manual capture |
| Public construction and game-development communities | Public communities and professional forums | Verified official access, if available and allowed | Permitted visible browser collection; otherwise manual capture |
| Official documentation, pricing, and release notes | Verification only | Verified official page, feed, or documentation access | Manual verification |
| Direct validation | Direct validation | Approved business email workflow | Manually sent platform messages or interviews |

Two websites in the same source category still count as one source type.

### 11.4 Prohibited Sources

Do not collect from:

- Instagram
- TikTok
- Pinterest
- YouTube

Do not use:

- Search-result snippets as qualifying evidence
- Vendor marketing as pain evidence
- Affiliate roundups as pain evidence
- Copied complaints
- Private groups or private messages without permission

### 11.5 Google and External Search

Approved queries may be executed through permitted search access. Every promising result must be opened at its original source before capture. If automated search-result collection is restricted or unavailable, the system creates a manual search task rather than bypassing restrictions.

### 11.6 Source Eligibility

Use a source only when the operator can determine:

- Who has the problem
- Whether the statement is first-hand
- When it was published
- Which workflow is affected
- Whether the complaint is specific
- Whether the source is independent of the vendor

Prefer:

- Recent, detailed reviews
- Concrete workflow descriptions
- Issue reports with reproducible context
- Threads with several distinguishable first-hand participants
- Reviews showing role, company size, product version, or use case
- Moderated communities with visible rules and history

Flag for caution:

- Anonymous or context-poor posts
- Incentivized reviews
- Highly emotional one-star reviews
- Generic five-star praise
- Vendor- or affiliate-dominated threads
- Complaints about obsolete product versions

Reject as qualifying evidence:

- Vendor marketing
- Affiliate roundups
- Copied complaints
- Search-result snippets
- Second-hand summaries
- Reaction counts without first-hand statements
- Undated content
- Content outside the approved source, language, geography, or age boundaries

### 11.7 Source-Family Collection Rules

#### 11.7.1 Structured Software-Review Platforms

For G2, Capterra, GetApp, and Software Advice:

1. The operator approves relevant software categories and products.
2. Start with available two- and three-star reviews and the newest ordering.
3. Also inspect specific one-star reviews for concrete workflow failures.
4. Inspect four- and five-star reviews for caveats and counterevidence.
5. Capture role, company size, use case, rating, date, positives, negatives, and product version when explicitly shown.
6. Flag reviews containing approved workaround, suite-tax, integration, platform, and data-control phrases.
7. Require full-review inspection before evidence approval.
8. Check newer complaints, current official documentation, and release notes before treating the problem as unresolved.

Two- and three-star reviews are a starting strategy, not a credibility shortcut.

#### 11.7.2 Reddit and Public Professional Forums

For every thread:

1. Capture the original post and direct URL.
2. Capture comments separately with their own public account labels and URLs when available.
3. Keep the original poster’s experience separate from each commenter.
4. Flag a commenter only when their text contains a candidate first-hand statement.
5. Never convert upvotes, awards, agreement-only replies, or thread popularity into evidence counts.
6. Capture current paid tools, switching, hired help, spreadsheets, chained tools, time estimates, missed deadlines, lost customers, or requests for alternatives when explicit.
7. Require operator review of disagreement, alternative solutions, and counterevidence.

Generic startup or SaaS communities may not serve as the primary source of customer pain unless the selected target users are describing their own work.

#### 11.7.3 Application and Extension Marketplaces

For Google Play, Chrome Web Store, Edge Add-ons, and Microsoft Store:

1. Search the approved workflow category.
2. Inspect direct competitors and adjacent tools.
3. Prefer newest ordering when available.
4. Start with low-to-middle ratings without excluding specific higher-rating caveats.
5. Capture application version, device, operating system, and platform context when shown.
6. Distinguish product defects, missing workflow support, platform limitations, pricing complaints, and temporary outages.
7. Check current release information or newer reviews before declaring the limitation current.

A generic crash report does not become an opportunity unless repeated evidence identifies a broader underserved workflow or platform gap.

#### 11.7.4 GitHub Issues and Discussions

Capture:

- Reporter’s actual use case
- Issue or discussion status
- Maintainer replies
- Linked and duplicate issues
- Version and platform details
- Workarounds
- Fix, closure, rejection, deferral, or unresolved status

Duplicate issue links remain one cluster unless distinct participants describe separate first-hand impacts. A maintainer implementation task is not automatically customer pain.

#### 11.7.5 Stack Overflow

Use Stack Overflow to detect:

- Repeated workaround complexity
- Cross-tool handoff failures
- Missing capability
- Platform incompatibility

A technical question alone never establishes willingness to pay. Commercial evidence must come from an approved signal, normally from another source or direct validation.

#### 11.7.6 Construction and Game-Development Communities

Before use, the operator confirms:

- Public access
- Visible dates
- Participants representing the selected segment
- Community rules permitting the collection method
- Research and outreach restrictions

Vendor-controlled forums are unsuitable unless independent criticism is clearly permitted. Apply the same full-thread, first-hand, independence, contact, and counterevidence rules used for public forums.

#### 11.7.7 Official Verification Sources

Official documentation, pricing, release notes, and support pages may verify:

- Current functionality
- Pricing
- Platform support
- Integration support
- Export or data-control options
- Whether a complaint was resolved

They never count as pain evidence.

## 12. Browser, Authentication, and Credentials

### 12.1 Dedicated Edge Profile

The automation uses one Edge profile dedicated to this workflow. It isolates:

- Cookies
- Authenticated sessions
- History
- Source-specific settings
- Automation extensions, if any are later approved

The operator performs login manually. The workflow never reads or stores account passwords.

### 12.2 Visible Browser Operation

Browser collection runs visibly by default so the operator can observe source behavior and take over when a permitted manual action is required.

The automation never:

- Solves or bypasses CAPTCHAs
- Evades authentication
- Rotates identities or proxies to avoid limits
- Circumvents robots controls
- Hides automation to defeat platform protections
- Continues after a clear access prohibition

### 12.3 Secret Storage

API tokens, OAuth refresh tokens, and email authorization material are stored only in Windows Credential Manager.

Secrets are prohibited in:

- Source code
- Configuration files
- SQLite record fields
- Google Sheets
- Logs
- Screenshots
- Error messages
- Backups outside protected credential storage

The implementation must request the least privilege the provider supports. Exact authorization scopes must be verified during implementation rather than assumed.

## 13. Respectful Access and Coverage

### 13.1 Sequential Collection

The system processes one source interaction at a time. Parallel page harvesting is prohibited.

### 13.2 Source-Specific Limits

Every adapter uses:

- Verified published limits when available
- Conservative operator-approved limits when published guidance is absent
- A maximum result or page count approved in the run configuration
- A maximum retry count
- A session stop condition

The design does not prescribe fabricated platform limits.

### 13.3 Retry Rules

Temporary network or server failures may be retried twice with increasing delays.

Do not automatically retry:

- CAPTCHA
- Access denial
- Authentication failure
- Account lock
- Rate-limit instruction requiring manual action
- Broken selector or unexpected schema
- Platform prohibition
- Consent or policy screen

These conditions pause the adapter and create a human-review task.

### 13.4 Manual Fallback

A manual task includes:

- Run ID
- Source
- Exact query
- Date window
- Coverage bound
- Required fields
- Reason automation stopped
- Last successful checkpoint

Manually entered evidence passes through the same review, duplicate, qualification, and audit controls.

## 14. Evidence Ingestion and Provenance

### 14.1 Candidate Capture

Permitted adapters may capture:

- Direct source URL
- Source-native identifier
- Public author or account label
- Publication date
- Public text
- Rating, version, platform, role, or company-size metadata when explicitly shown
- Matched deterministic phrase
- Capture time
- Content hash

The capture remains a Candidate until reviewed.

### 14.2 Required Human Evidence Review

The reviewer must confirm:

- The full source was opened.
- The statement is first-hand.
- The exact excerpt is accurate.
- The publication date is reliable.
- The user context is relevant.
- The workflow and problem are specific.
- The evidence is applicable to the approved market.
- The statement is not duplicated.
- The issue is not clearly resolved.
- Contact capture, if any, follows the public-professional rules.

### 14.3 Approved Evidence Snapshot

For approved evidence, retain:

- Source URL
- Exact public excerpt
- Public metadata
- Capture timestamp
- Content hash
- A permitted screenshot or snippet stored locally
- Human approval

Do not archive an entire page unless necessary, permitted, and specifically approved.

### 14.4 Unapproved Candidate Retention

Raw unapproved candidate captures are deleted 30 days after their final review decision.

Retain:

- Candidate ID
- Source
- Decision
- Decision reason
- Deterministic rule that flagged it
- Audit history

### 14.5 Removed or Unavailable Sources

When a previously approved source becomes unavailable:

1. Mark the Evidence Item `Source Unavailable`.
2. Preserve its provenance and permitted local snapshot.
3. Remove it from current qualification counts until human reapproval.
4. Create a review task.
5. Record whether corroborating current evidence remains.

The system never silently continues counting unavailable evidence.

## 15. Recency Processing

For every run:

- `12-month cutoff = run date minus 12 months`
- `36-month cutoff = run date minus 36 months`

Assign:

- `Recent` when the publication date is on or after the 12-month cutoff.
- `Older—Confirmed Current` when the date is before the 12-month cutoff but on or after the 36-month cutoff and current recurrence has been human-confirmed.
- `Context Only—Too Old` when the date is before the 36-month cutoff.
- `Context Only—Date Unclear` when the date cannot be established.

An opportunity requires:

- At least two of five independent users with `Recent` evidence.
- Remaining qualifying evidence no older than 36 months.
- Human-confirmed recent recurrence before older evidence counts.

Dates and bands are calculated deterministically. Whether older evidence reflects the same underlying current problem remains a human decision.

## 16. Deterministic Pain-Signal Rules

### 16.1 Rule Types

The deterministic engine may use:

- Exact phrase matches
- Case-insensitive keyword matches
- Approved word stems
- Regular expressions for explicit time, money, version, and platform patterns
- Structured source fields
- Approved product, competitor, workflow, and platform dictionaries

### 16.2 Rule Output

A match may:

- Flag a candidate
- Highlight the matching sentence
- Suggest a controlled pain category
- Identify explicit numeric text
- Identify an explicit product or platform mention

A match may not:

- Establish that the statement is first-hand
- Infer an unstated workaround or consequence
- Declare a commercial signal
- Determine user intent
- Decide that two paraphrases mean the same thing
- Assign evidence credibility

### 16.3 Human-Confirmed Meaning Fields

The operator confirms:

- User type
- Job or desired outcome
- Workflow stage
- Failure or constraint
- Workaround
- Consequence
- Commercial-signal type
- Current relevance

Unrecognized paraphrases are a disclosed deterministic limitation and an Instance 3 candidate.

## 17. Duplicate and Independence Controls

### 17.1 Automatic Exact-Duplicate Flags

The system flags:

- Repeated source-native IDs
- Repeated canonical URLs
- Repeated exact excerpts
- Repeated content hashes
- Previously approved source-local account plus Pain Cluster combinations
- Known quoted copies linked to an original record

### 17.2 Human-Required Duplicate Decisions

Human approval is required when:

- Two accounts may represent the same person.
- The same person may have posted on multiple platforms.
- Several people may describe one organizational incident.
- A repost may materially modify an original complaint.
- Similar text may be coincidence rather than copying.
- Several participants at one company may have distinct impacts.

### 17.3 Independence Rules

- Count one person once per Pain Cluster.
- Several posts by the same person enrich one user’s evidence.
- A contacted user’s reply enriches that user’s record and does not create another independent user.
- Copied or quoted complaints count only at the original source.
- A shared organizational incident counts once unless distinct first-hand impacts are approved.
- A distinct outreach participant may count only when first-hand evidence meets every normal rule.

No cross-platform identity matching is performed without an explicit public link and human approval.

## 18. Pain Clustering

### 18.1 Required Normalization

The reviewer completes:

`[USER] cannot reliably [JOB] because [WORKFLOW FAILURE], causing [CONSEQUENCE], so they currently [WORKAROUND].`

This normalized statement never replaces the exact excerpt.

### 18.2 Four-of-Five Rule

Evidence may join one Pain Cluster only when at least four of these five elements match:

1. User type
2. Desired job
3. Workflow stage
4. Failure or constraint
5. Consequence

The system may compare exact controlled values and display candidate matches. The operator makes the final clustering decision.

### 18.3 Separation Rule

Do not combine complaints merely because they mention the same tool, company, category, or desired feature. Materially different workflow failures remain separate Pain Clusters.

Every accepted or rejected cluster-membership decision is audited.

## 19. Lead Creation and Promotion

### 19.1 Lead Creation

Create a Lead only after human approval confirms:

- At least one credible first-hand Evidence Item
- A specific target user
- A specific job or desired outcome
- A meaningful workflow problem
- A plausible consequence
- A documented validation gap

The system creates the Lead record and calculates its current:

- Independent-user count
- Source-type count
- Recent-evidence count
- Commercial-signal count

### 19.2 Lead Strengthening

The system may generate approved opposing and neutral query templates, including searches for:

- The problem being fixed
- A tool now supporting the missing capability
- A workflow working well with an existing tool
- Current adequate alternatives

Queries require normal preview and run approval.

### 19.3 Promotion Eligibility

A Lead becomes eligible for qualification review only when it has:

- Five independent users
- At least two source types
- At least two Recent evidence items
- At least one approved commercial signal
- A completed light competitor check

Eligibility opens gate review. It does not create a Qualified Opportunity by itself.

### 19.4 Promotion

Promote only after:

- Every pass/fail gate passes
- Every scoring rating is complete
- The total score and band are calculated
- Required quality checks pass
- The promotion is recorded in the audit trail

## 20. Commercial-Signal Processing

The deterministic engine may flag explicit text matching these categories:

- Current payment for an inadequate tool
- Payment for a workaround or manual help
- Measurable labor or monetary waste
- Revenue, delivery, or customer-service delay
- Active replacement search
- Explicit budget or conditional willingness to pay
- Acceptance of a paid-pilot or standardized-service discussion

The operator must confirm the signal and its supporting excerpt.

Do not qualify:

- General enthusiasm
- Upvotes or likes
- “Cool idea” comments
- Unsupported hypothetical willingness to pay
- Popularity metrics

No-response outreach remains neutral.

## 21. Light Competitor Check

Begin after the pain threshold is met or nearly met.

### 21.1 Deterministic Collection

Using normal source-access controls, collect current, decision-critical facts for:

- Direct competitors
- Adjacent tools
- Manual and spreadsheet workarounds
- Productized services
- Free or open-source alternatives

Record:

- Target customer
- Supported platforms
- Current pricing structure
- Local, cloud, or hybrid operation
- Data export and user-control options
- Relevant integrations
- Complexity
- Current unresolved complaints
- Source URL
- Verification date

Official documentation, pricing, and release notes verify facts but do not count as pain evidence.

### 21.2 Human Gap Decision

The operator selects:

- `Unserved`
- `Underserved`
- `Served`
- `Unclear`

`Served` fails the Current-Gap gate. `Unclear` prevents qualification until resolved.

This remains a light check, not full market sizing or a deep competitive study.

## 22. Pass/Fail Gate Engine

Every gate is applied before scoring.

### Gate 1: Target Fit

Pass only if the user belongs to an approved segment and the market rewards competency and product quality.

### Gate 2: Industry Fit

Fail education, finance, legal, government, reputation-dependent, licensing-dependent, clearance-dependent, or comparable high-barrier markets.

### Gate 3: Market and Language Fit

Pass only when the evidence reasonably applies to U.S. English-language customers.

### Gate 4: Product or Service Fit

Pass only when the response can be a focused approved software product, productized service, or standardized service.

### Gate 5: Platform Fit

For software, pass only when official support can focus on Windows, Linux, Android, or an approved subset. Incidental macOS or iOS web access is acceptable; official targeting is not.

### Gate 6: Data-Control Fit

Fail if the opportunity inherently requires:

- Selling user data
- Mandatory cloud processing without user choice
- Preventing practical data export
- Unnecessary loss of user control

### Gate 7: Solo-Build Fit

Pass only when an initial usable version appears achievable by one founder in roughly three months using current resources and AI-assisted development.

### Gate 8: Pre-Revenue Cost Fit

Pass only when the product can begin with free tools and existing subscriptions. Later revenue-funded operating costs are allowed.

### Gate 9: Solo-Operations Fit

Fail if the likely model requires employees, contractors, a large sales organization, constant support, or extensive custom delivery.

### Gate 10: Evidence Fit

Pass only with five independent users, two source types, current recurrence, and a commercial signal.

The engine verifies the exact counts from approved evidence.

### Gate 11: Problem Specificity

Fail vague feature wishes, generic dissatisfaction, and solution requests lacking repeated workflow pain and meaningful consequences.

### Gate 12: Current-Gap Fit

Fail when current accessible alternatives adequately solve the problem for the target user.

### 22.1 Gate Ownership

The system may deterministically precheck required counts and missing fields. The operator approves every judgment-based gate.

Each gate requires:

- Pass or fail
- Supporting evidence
- Rationale
- Approver
- Rule version
- Timestamp

A failed gate:

- Is stored explicitly.
- Prevents scoring.
- Moves the Lead to Rejected or Archived as approved.
- Is never converted into a numerical penalty.

## 23. Weighted 100-Point Scoring Engine

Score only after every gate passes.

### 23.1 Rating Scale

The operator rates each subcriterion from 0 to 5:

- `0` — no supporting evidence or strong contrary evidence
- `1` — very weak
- `2` — limited
- `3` — credible
- `4` — strong
- `5` — exceptional

The engine calculates:

`Subcriterion points = rating ÷ 5 × maximum points`

Round the final total to one decimal place.

### 23.2 Evidence Strength and Problem Severity — 35 Points

- Independent-user and source diversity: 8
- Recency and recurrence: 7
- Severity of time, money, error, delay, or delivery impact: 10
- Specificity and burden of the current workaround: 6
- Survival after counterevidence and current-product checks: 4

### 23.3 Solo Buildability and Operability — 30 Points

- Initial scope achievable in roughly three months: 10
- Sustainable solo operation and support: 7
- No upfront or pre-revenue spending: 6
- Fit with current technical resources and approved platforms: 4
- Fit with local-first, data-sovereignty, and user-control principles: 3

### 23.4 Commercial Strength — 20 Points

- Existing spend or paid workaround: 6
- Measurable labor or monetary cost: 5
- Revenue, delivery, or customer-service impact: 5
- Clear buyer and plausible revenue model: 4

### 23.5 Competitive Viability and Customer Accessibility — 15 Points

- Clear unresolved gap or focused differentiation: 6
- Reachable target users and communities: 4
- Self-service or low-touch acquisition fit: 3
- Manageable switching or migration burden: 2

### 23.6 Priority Bands

- `85.0–100`: Priority A — strongest standalone candidate
- `70.0–84.9`: Priority B — strong candidate with manageable validation gaps
- `55.0–69.9`: Priority C — qualified but secondary
- `Below 55.0`: Qualified Hold — evidence threshold met but not currently attractive enough to prioritize

### 23.7 Tie-Breakers

Apply in this exact order:

1. Stronger evidence and severity score
2. Standalone opportunity over portfolio addition
3. Lower solo-operating burden
4. Stronger local-first and user-control fit
5. More recent recurrence
6. Windows, Linux, browser, or focused web opportunity over Android-only opportunity
7. Direct-payment model over advertising-dependent model

An advertising-dependent opportunity may outrank a direct-payment opportunity only when its total benefit and evidence are materially stronger and its advertising preserves privacy and never sells user data.

### 23.8 Traceability

Every rating requires:

- Human rationale
- Supporting Evidence IDs
- Counterevidence IDs
- Rating author
- Rating timestamp

The engine records every formula input and output.

## 24. Ranking, Backlog, and Bias Controls

### 24.1 Ranking and Backlog Maintenance

The Ranking Engine:

1. Selects only Qualified Opportunities.
2. Sorts by total score.
3. Applies tie-breakers in order.
4. Separates standalone opportunities, Qualified Holds, and Portfolio Additions.
5. Publishes rank and reason.
6. Synchronizes the result to Sheets.

Re-score when:

- New independent evidence appears.
- A competitor changes pricing or functionality.
- Platform support changes.
- The workaround changes.
- Build or operating assumptions change.
- A source becomes unavailable.
- A previously failed gate is legitimately reopened.

Historical scores remain auditable.

### 24.2 Bias and Noise Controls

The system and reviewer enforce:

1. **Loud-Minority Control**
   - One intense complaint remains one user.

2. **Rating-Bias Control**
   - Two- and three-star reviews are a starting point.
   - Specific evidence and counterevidence from other ratings remain eligible.

3. **Duplicate Control**
   - Repeated wording is traced to the earliest accessible source.
   - The original person counts once.

4. **Source-Concentration Control**
   - Two source types are mandatory.
   - Several websites within one source category do not satisfy diversity.

5. **Company-Incident Control**
   - Several people discussing one organizational incident are not automatically several independent market occurrences.

6. **Outdated-Complaint Control**
   - Current documentation, releases, and recent user evidence are checked before an older limitation is treated as active.

7. **Solution-First Bias Control**
   - The reviewer preserves the user’s actual job, failure, consequence, and workaround rather than reshaping evidence to fit a preferred product.

8. **Feature-Wish Control**
   - A feature request counts only when it exposes repeated workflow pain, a consequential workaround, current recurrence, and commercial relevance.

9. **Popularity Control**
   - Upvotes, likes, reply volume, search ranking, and download counts remain context rather than independent evidence.

10. **Outreach-Response Bias Control**
    - Contact availability never raises rank.
    - Silence never disproves demand.

11. **Founder-Fit Control**
    - An attractive market still fails when it conflicts with solo operation, three-month scope, zero pre-revenue spending, approved industries, approved platforms, or user-control principles.

## 25. Portfolio Reserve

A Portfolio Addition:

- Remains secondary to a standalone opportunity.
- Links to a qualified primary Opportunity ID when such an opportunity exists.
- Records why it is not independently strong enough.
- Never becomes the principal result merely to fill a quota.

If no suitable standalone opportunity exists, keep the item in the Portfolio Reserve with a reconsideration condition.

## 26. Zero-Qualified-Opportunity Handling

The system never lowers thresholds to produce an opportunity.

When no opportunity qualifies, publish:

`Zero Qualified Opportunities — evidence and quality thresholds were not lowered.`

The run still retains:

- Coverage
- Queries
- Evidence
- Leads
- Counterevidence
- Rejections
- Failed gates
- Stopping reason
- Quality-control result

Zero is a successful integrity-preserving output, not a system failure.

## 27. Public Professional Contact Capture

### 27.1 Allowed Routes

- Public platform profile
- Platform DM route
- Public business email
- Public professional-profile messaging
- Company website
- Company contact form

### 27.2 Prohibited Practices

- Guessed email addresses
- Purchased or brokered data
- Private personal information
- Deanonymization
- Unlinked cross-platform identity matching
- Personal contact details unrelated to professional communication

### 27.3 Capture Procedure

An adapter may flag an explicit public route. Before use, the operator confirms:

- The route is public.
- The route is professional.
- The source clearly links it to the person or company.
- The source and channel permit the intended contact.
- No opt-out or prohibition exists.

Store the Contact-source URL for every route.

Contact availability:

- Is optional
- Does not affect evidence validity
- Does not increase independent-user counts
- Must not alter scoring

## 28. Contact Data, Privacy, and Retention

### 28.1 Storage

Google Sheets may contain:

- Public professional contact route
- Channel type
- Contact-source URL
- Outreach state
- Factual response summary
- Consent status

Keep locally:

- Full private replies
- Message artifacts
- Provider delivery details
- Local evidence snapshots

Private replies are not public quotations.

### 28.2 Retention

Delete exact contact routes 12 months after the related Lead, Opportunity, and outreach record become inactive.

Retain:

- Evidence provenance
- Outreach dates and outcomes
- Audit history
- Consent status
- A minimal suppression identifier for opt-outs

The suppression identifier must be sufficient to prevent recontact while minimizing retained contact data.

### 28.3 Access Control

- Local files are restricted to the operator’s Windows account.
- The Google Sheet remains private to the operator’s Google account.
- Credentials remain in Windows Credential Manager.
- Backups receive the same access restrictions as primary data.
- Private reply content never appears in general logs or email notifications.

## 29. Outreach Preparation and Approval

### 29.1 Eligibility

Create an outreach record only when:

- The complaint belongs to a recorded Pain Cluster.
- A permitted public professional route exists.
- The source and channel allow contact.
- The message can reference the specific public statement.
- No opt-out, delivery failure, or prohibition exists.

Use one professional channel per person.

### 29.2 Deterministic Message Preparation

The system populates the templates in this section for:

1. Problem-validation interview
2. Beta or waitlist invitation
3. Paid pilot or standardized-service offer
4. One follow-up

It may insert only approved fields:

- Name or public professional label
- Specific public workflow problem
- Tool or workflow
- Target user type
- Approved product or service description
- Honest scope
- Actual timeline
- Actual price
- Actual exclusions
- OnTheLLow identity

Missing required fields prevent approval. The system does not invent personalization or product claims.

### 29.3 Stage Rules

#### Stage 1: Problem Validation

Permit when:

- A Lead has at least three credible independent signals, or
- A Qualified Opportunity needs deeper workflow detail.

The objective is to verify:

- Last real occurrence
- Current workaround
- Consequence
- Decision-maker
- Minimum worthwhile outcome

Template:

```text
Subject: Quick question about [SPECIFIC_WORKFLOW_PROBLEM]

Hi [RECIPIENT_NAME],

I saw your public [REVIEW_POST_OR_COMMENT] about [SPECIFIC_PROBLEM] while using [TOOL_OR_WORKFLOW]. I am researching this problem for [TARGET_USER_TYPE] and wanted to ask whether it is still affecting your work.

Would you be open to answering three short questions by message or having a 15-minute conversation? I am validating the problem first, not claiming that a finished solution already exists.

If this is not relevant anymore, no response is needed.

[SENDER_NAME]
OnTheLLow
```

Validation questions:

1. When did this problem last occur, and what were you trying to complete?
2. What do you currently do instead, and what does that cost in time, money, errors, or delay?
3. What minimum outcome would make a focused solution worth testing or paying for?

#### Stage 2: Beta or Waitlist

Permit only after the person:

- Confirms the problem, and
- Expresses interest.

Do not claim development, features, pricing, security, or availability that does not exist.

Template:

```text
Hi [RECIPIENT_NAME],

Thank you for explaining how [PROBLEM] affects [WORKFLOW]. I am [EVALUATING_OR_BUILDING] a focused [PRODUCT_OR_SERVICE_TYPE] intended to [SPECIFIC_OUTCOME] for [TARGET_USER].

The current concept would:

- [CORE_OUTCOME_1]
- [CORE_OUTCOME_2]
- [DATA_CONTROL_OR_PLATFORM_COMMITMENT]

It would not attempt to replace [UNRELATED_LARGE_SUITE_OR_WORKFLOW].

Would you like to join a small [BETA_OR_WAITLIST] and review the scope before anything is finalized?

[SENDER_NAME]
OnTheLLow
```

#### Stage 3: Paid Pilot or Standardized Service

Permit only when:

- The problem is qualified.
- The person expressed interest.
- The offer has a defined scope.
- The founder can deliver it with current resources.
- Price, timing, data handling, exclusions, and limitations are honest.

Template:

```text
Hi [RECIPIENT_NAME],

Based on the workflow you described, I can offer a limited [PAID_PILOT_OR_STANDARDIZED_SERVICE] focused on [SPECIFIC_OUTCOME].

Scope:
- [DELIVERABLE_1]
- [DELIVERABLE_2]
- [PLATFORM_OR_DATA_CONTROL_BOUNDARY]

Not included:
- [EXCLUSION_1]
- [EXCLUSION_2]

Timeline: [HONEST_TIMELINE]
Price: [ACTUAL_PRICE]
Success check: [MEASURABLE_ACCEPTANCE_RESULT]

If this scope matches your need, the next step is [LOW_FRICTION_NEXT_ACTION]. If it does not, there is no obligation.

[SENDER_NAME]
OnTheLLow
```

### 29.4 Message-Specific Approval

Every initial message and follow-up requires separate approval.

The approval binds:

- Contact route
- Recipient
- Stage
- Full message content
- Message content hash
- Public-problem reference
- Opportunity or Lead
- Approval timestamp

Any change invalidates approval.

Batch approval is prohibited.

## 30. Outreach Sending and Follow-Up

### 30.1 Business Email

An approved business email may be sent automatically through the OnTheLLow Google Workspace business mailbox after:

- Current approval validation
- Suppression check
- Channel-limit check
- Stage check
- Content-hash check
- Provider authorization check

The system records the provider message or thread identifier without logging credentials.

### 30.2 Browser Channels

For:

- Platform DMs
- Professional-profile messages
- Company contact forms

The system may open the approved route and prepare the approved message. The operator must perform the final submission manually.

The operator records successful submission before the state becomes `Sent`.

### 30.3 Follow-Up Rule

Permit:

- One initial message
- One follow-up after seven calendar days

The system prepares, but does not preapprove, the follow-up.

Fresh approval is required.

Template:

```text
Hi [RECIPIENT_NAME],

I am following up once regarding my note about [SPECIFIC_WORKFLOW_PROBLEM]. If the issue is still relevant, I would value a brief reply or 15-minute conversation.

If not, no response is needed and I will not follow up again.

[SENDER_NAME]
OnTheLLow
```

Cancel the follow-up after:

- Any response
- Rejection
- Opt-out
- Delivery failure
- Platform prohibition
- Confirmation that the problem is no longer relevant

### 30.4 Response Monitoring

The email adapter may check dedicated outreach threads or labels for:

- Replies
- Delivery failures
- Opt-outs

Use the least provider access available and process only dedicated outreach records.

DM and contact-form responses are updated manually.

### 30.5 Evidence Treatment

- A reply from an already counted person enriches the existing Evidence Item.
- It does not create another independent user.
- A distinct participant counts only after normal evidence approval.
- No response is neutral.
- A private reply is summarized factually unless quotation permission is explicit.
- Willingness to test or pay records the exact conditions.
- Rejection and counterevidence receive the same care as positive replies.

## 31. Opt-Out Suppression

When an opt-out is detected or recorded:

1. Set the outreach record to `Closed—Opted Out`.
2. Cancel every pending message and follow-up for that person.
3. Prevent new outreach using the same public route or approved identity.
4. Store only the minimum suppression identifier required.
5. Record source, time, and actor.
6. Synchronize the suppression status without exposing unnecessary private content.

No manual override may authorize further outreach unless the person later provides explicit, recorded consent.

## 32. Stopping Conditions

### 32.1 Coverage Bounds

Every query family or source batch has an approved maximum result or page count.

A batch is complete only when:

- Its approved bound is reached, or
- The source has no more accessible results, or
- A documented access restriction ends collection, or
- The operator ends it with a recorded reason.

### 32.2 No-New-Theme Sequence

After human review of a completed batch:

- A newly approved Pain Cluster resets the sequence to zero.
- Evidence that only strengthens an existing cluster does not count as a new theme.
- A batch producing no new Pain Cluster increments the sequence.
- Two consecutive completed batches without a new Pain Cluster satisfy the no-new-theme condition.

The system does not determine semantic novelty before the human clustering decision.

### 32.3 Run Closure

Close a run only when:

1. Every planned source type has reached its approved coverage state.
2. Recent-window searches are complete.
3. Older-window searches occurred only where justified.
4. Two consecutive reviewed batches produced no new pain theme.
5. Promising clusters received counterevidence checks.
6. Every capture is classified.
7. Every Lead has a documented evidence gap.
8. Every eligible cluster completed competitor review, gates, and scoring.
9. Contact availability was checked only within approved boundaries.
10. Final quality control passes.

Otherwise the run remains:

- `Paused—Human Action`
- `Incomplete`
- `Failed`

### 32.4 Early Stop

Stop earlier when:

- The selected market violates a hard exclusion.
- Suitable public evidence is unavailable.
- Responsible access is unavailable.
- The problem is clearly resolved.
- Current adequate alternatives eliminate the gap.

Never continue merely to reach a preferred number of opportunities.

### 32.5 Required Run Outputs

Every closed run produces:

1. **Run Record**
   - Segment
   - Workflows
   - Date boundaries
   - Sources
   - Queries
   - Coverage limitations
   - Stopping reason

2. **Evidence Set**
   - Counting evidence
   - Context-only evidence
   - Counterevidence
   - Duplicate decisions
   - Public professional contact availability

3. **Lead List**
   - Pain statement
   - Evidence status
   - Missing validation
   - Next action

4. **Ranked Qualified Opportunities**
   - Gate results
   - Category and total scores
   - Priority band
   - Rank
   - Main evidence
   - Main risk
   - Recommended next validation

5. **Rejected and Archived List**
   - Failed gate or rejection reason
   - Reconsideration trigger

6. **Portfolio Reserve**
   - Secondary items
   - Related primary opportunity when available
   - Evidence status
   - Reason not standalone

7. **Outreach Record**
   - Approved public professional routes
   - Outreach stage
   - One-follow-up status
   - Responses
   - Additional evidence
   - Opt-outs

8. **Automation Record**
   - Adapter versions
   - Rule versions
   - Failures
   - Retries
   - Manual fallbacks
   - Approvals
   - Audit correlation ID

## 33. Notifications

Send Windows and email notifications for:

- Scheduled run awaiting approval
- On-demand run awaiting approval
- Queued run blocked by an unfinished run
- Source requiring manual action
- Authentication or access failure
- Adapter or page-structure failure
- Sheet synchronization conflict
- Evidence or gate review awaiting action
- Outreach awaiting approval
- Follow-up due
- Opt-out or delivery failure
- Run completed
- Run incomplete or failed
- Backup or recovery failure

Notifications contain record IDs and safe summaries, not credentials or full private replies.

## 34. Error Handling

### 34.1 Source Failure

- Stop the affected adapter.
- Commit the last successful checkpoint.
- Preserve already captured records.
- Mark coverage incomplete.
- Continue unaffected sources when safe.
- Block qualification that depends on missing coverage or source diversity.
- Notify the operator.
- Create a manual fallback task.

### 34.2 Authentication Failure

- Stop the adapter.
- Do not retry automatically.
- Open a manual reauthentication task.
- Resume only after the operator confirms successful login.

### 34.3 CAPTCHA or Access Denial

- Stop automated interaction.
- Record the page and source.
- Do not solve, bypass, or repeatedly retry.
- Route the work to permitted manual collection or exclude the source.

### 34.4 Selector or Schema Change

- Fail closed when required fields disappear or map unexpectedly.
- Quarantine the capture batch.
- Disable only the affected adapter.
- Run saved-fixture and updated-fixture validation before re-enabling it.

### 34.5 Database Failure

- Stop state-changing work.
- Do not send outreach.
- Preserve the last committed transaction.
- Validate the database.
- Restore from the latest known-good backup only after operator confirmation.

### 34.6 Sheet Conflict

- Keep SQLite unchanged.
- Mark the row conflicted.
- Display both versions.
- Require a human resolution.
- Audit the resolution.

### 34.7 Outbound Failure

- Do not assume delivery.
- Record provider or manual failure.
- Cancel follow-up when the route rejects the message.
- Require a new approved route before any later contact.
- Preserve the one-channel rule.

## 35. Retry and Recovery

### 35.1 Checkpoints

Create a durable checkpoint after:

- Run approval
- Query approval
- Every completed source item or bounded batch
- Every evidence decision
- Every cluster decision
- Every gate decision
- Score completion
- Every outbound transition
- Every Sheet synchronization batch

### 35.2 Idempotent Resume

On restart:

1. Read the last committed checkpoint.
2. Confirm record and adapter versions.
3. Skip completed records.
4. Resume the next incomplete action.
5. Reject duplicate inserts using immutable IDs and source-native keys.
6. Record a recovery event.

No completed source record is replayed unless the operator requests a versioned recheck.

## 36. Logs and Audit Trail

### 36.1 Append-Only Events

Record:

- System actions
- Human actions
- Approvals
- Rejections
- Corrections
- Overrides
- Source access attempts
- Retry decisions
- State transitions
- Rule changes
- Adapter changes
- Synchronization results
- Notification delivery
- Outreach transitions

### 36.2 Manual Overrides

An override requires:

- Record ID
- Original value
- Proposed value
- Reason
- Operator identity
- Timestamp

The original value remains preserved. An override cannot:

- Bypass a prohibited source
- Authorize CAPTCHA or access-control evasion
- Ignore an opt-out
- Count unapproved evidence
- Score an opportunity with a failed gate
- fabricate missing evidence

### 36.3 Rule Traceability

Every deterministic result references:

- Input record IDs
- Rule version
- Formula version
- Adapter version when applicable
- Output record
- Timestamp

## 37. Backup and Data Recovery

Create protected local backups:

- Immediately before every run
- Immediately after every successfully closed run

Retain:

- The latest 12 backups
- One monthly snapshot for 24 months

Backups include:

- SQLite database
- Rule and configuration registry
- Approved local evidence artifacts
- Audit history
- Synchronization state

Do not export Credential Manager secrets into backups.

Test restoration with synthetic or test data before relying on the backup process.

## 38. Security and Privacy Controls

- Bind the dashboard only to the local loopback interface.
- Restrict local files to the operator’s Windows account.
- Keep the Sheet private.
- Use least-privilege provider authorization.
- Store tokens only in Windows Credential Manager.
- Never store passwords in workflow data.
- Never place secrets in logs, notifications, or screenshots.
- Never use data brokers.
- Never deanonymize public accounts.
- Never sell collected or future customer data.
- Minimize stored contact information.
- Delete inactive contact routes on schedule.
- Keep full private replies local.
- Preserve opt-outs through minimal suppression records.
- Require human approval before every outbound message.
- Invalidate approval whenever message content or route changes.

## 39. Cost Controls

The workflow must use:

- The existing Windows computer
- Free software
- Free, permitted source access
- Existing Google Workspace access
- Existing business email
- Existing subscriptions only when already paid for

Do not require:

- Paid scraping services
- Paid proxies
- CAPTCHA-solving services
- Contact-data brokers
- Hosted databases
- Paid schedulers
- Paid automation platforms
- Paid source APIs
- New pre-revenue infrastructure

When a free limit is exhausted:

- Pause the affected function.
- Notify the operator.
- Use a permitted manual fallback.
- Do not silently incur charges.

## 40. Deployment and Maintenance

### 40.1 Deployment Form

Package the Python system as a local Windows application with:

- Desktop shortcut
- Private local dashboard
- Background worker
- Windows Task Scheduler registration
- Dedicated Edge profile setup
- SQLite database initialization
- Google Sheets connection setup
- Google Workspace email authorization
- Credential Manager integration
- Backup location configuration

No hosted server is required.

### 40.2 Adapter Isolation

Each source adapter has:

- Separate version
- Separate fixture set
- Separate health state
- Separate access manifest
- Separate fallback

A broken adapter cannot automatically modify itself or unrelated adapters.

### 40.3 Updates

Updates require:

- Reviewed source-access status
- Reviewed rule changes
- Fixture tests
- Migration tests when data changes
- Changelog
- Operator approval
- Recoverable rollback package

Automatic self-modification is prohibited.

### 40.4 Maintenance Responsibility

The sole operator owns:

- Run approvals
- Source-access reviews
- Adapter re-enablement
- Rule changes
- Data-retention review
- Backup review
- Software updates

Coding assistance may help implement or maintain the system later, but it does not receive autonomous production authority.

## 41. Test Strategy

### 41.1 Offline Unit Tests

Test:

- Date cutoffs and recency bands
- Source-type mappings
- Evidence counts
- Independent-user controls
- Exact-duplicate detection
- Required source diversity
- Gate blocking
- Scoring formulas
- One-decimal rounding
- Priority bands
- Tie-break order
- Weekly rotation
- Missed-start behavior
- Queue concurrency
- Outreach limits
- Seven-day follow-up
- Follow-up cancellation
- Opt-out suppression
- Retention deadlines
- Backup rotation
- State transitions

### 41.2 Adapter Fixture Tests

Use saved, permitted, sanitized pages or responses to test:

- Required field extraction
- Missing fields
- Date parsing
- Pagination bounds
- Duplicate source IDs
- Unexpected page structures
- Selector changes
- Failure isolation

### 41.3 Integration Tests

Use a test database and test Sheet to verify:

- Outbound synchronization
- Authorized inbound edits
- Stale edit rejection
- Mobile approval validation
- Checkpoint recovery
- Idempotent resume
- Partial-source failure
- Audit events
- Notifications

### 41.4 Outreach Tests

- Use only the operator’s own test email accounts.
- Never send tests to real prospects.
- Verify message-specific approval.
- Verify content-hash invalidation.
- Verify one-channel enforcement.
- Verify reply, failure, and opt-out cancellation.
- Simulate DMs and contact forms without real submission.

### 41.5 Live Source Tests

Live read-only tests require explicit operator approval during implementation.

They must:

- Use minimum necessary volume
- Respect confirmed source rules
- Avoid real outreach
- Stop on access friction
- Record that the capability was tested

This workflow document does not claim that any source capability has been tested.

## 42. Acceptance Criteria

The system is acceptable only when tests demonstrate that:

1. No scheduled or on-demand collection begins without current run approval.
2. Only one run collects at a time.
3. Weekly priorities rotate `1 → 2 → 3 → 4` without on-demand interference.
4. A missed weekly trigger becomes pending at next startup.
5. No Candidate Capture affects evidence counts before human approval.
6. Five independent users, two source types, two recent items, and one commercial signal are enforced exactly.
7. Evidence older than 36 months cannot qualify.
8. Older qualifying evidence requires current recurrence.
9. Two websites in one category count as one source type.
10. Failed gates block scoring.
11. Every score uses the confirmed weights and formula.
12. Priority bands and tie-breakers execute in the confirmed order.
13. Duplicate users, copied complaints, and shared incidents cannot be silently overcounted.
14. Counterevidence remains linked and visible.
15. Portfolio additions remain secondary.
16. Zero qualified opportunities is a valid completed result.
17. Contact availability never affects evidence or scoring.
18. No guessed, brokered, private, or deanonymized contact route is accepted.
19. Every outbound message requires separate, current approval.
20. Browser channels cannot auto-submit.
21. No more than one initial message and one seven-day follow-up are permitted.
22. Replies, rejection, opt-out, failure, and prohibition cancel follow-ups.
23. Opt-out suppression survives contact-route deletion.
24. Restart recovery creates no duplicate records or messages.
25. Access denials, CAPTCHAs, and broken adapters fail closed.
26. SQLite and Sheet conflicts preserve SQLite until human resolution.
27. Every automated decision is traceable to inputs and a versioned rule.
28. Credentials and full private replies never enter logs or Sheets.
29. The workflow operates without new pre-revenue spending.
30. A run cannot be marked complete while required coverage or review remains incomplete.

## 43. Operating Runbook

### 43.1 Weekly Run

1. Monday at 10:00 a.m. Eastern, create the next scheduled priority run.
2. If the computer was off, create it at next startup.
3. If another run is active, queue it.
4. Notify the operator.
5. Operator selects the narrow segment and one to three workflows.
6. System generates the proposed source plan and exact queries.
7. Operator approves sources, queries, coverage bounds, and fallbacks.
8. System performs adapter preflight checks.
9. Create a pre-run backup.
10. Collect one source interaction at a time.
11. Pause affected adapters on prohibited or ambiguous access.
12. Present Candidate Captures for review.
13. Operator approves evidence, duplicates, independence, and cluster membership.
14. System updates Leads and qualification counts.
15. Perform counterevidence and competitor checks where required.
16. Operator completes gate decisions and ratings.
17. System calculates scores, bands, tie-breaks, and rankings.
18. Review contact-route candidates.
19. Prepare outreach only for eligible records.
20. Require message-specific approval and the correct sending method.
21. Complete stopping-condition and final-quality checks.
22. Close as Completed, Incomplete, or Failed.
23. Synchronize Sheets.
24. Create the post-run backup when successfully closed.
25. Notify the operator.

### 43.2 On-Demand Run

Use the same process. Mark the origin `On-Demand`. Do not advance or reorder the weekly priority rotation.

### 43.3 Manual Collection

1. Open the generated manual task.
2. Navigate through the dedicated profile or ordinary permitted browser access.
3. Collect only the requested public fields.
4. Enter the direct URL and exact excerpt.
5. Submit the record as a Candidate Capture.
6. Complete normal human review.

### 43.4 Failed Adapter

1. Do not repeatedly rerun it.
2. Review the failure and access manifest.
3. Use manual fallback if allowed.
4. Update fixtures and the adapter only through the reviewed maintenance process.
5. Re-enable after tests and operator approval.

### 43.5 Outreach

1. Confirm eligibility and one-channel status.
2. Review deterministic draft.
3. Correct any placeholder or unsupported claim.
4. Approve the exact message.
5. Send approved business email or manually submit the browser channel.
6. Record delivery.
7. Monitor the dedicated email thread or manually update other channels.
8. Prepare one follow-up after seven days only when still permitted.
9. Require fresh approval.
10. Close after response, follow-up, rejection, opt-out, failure, or prohibition.

## 44. Manual-to-Automated Traceability

| Manual stage | Automated component or rule | Input | Output | Human checkpoint | Failure fallback | Audit record |
|---|---|---|---|---|---|---|
| Select segment | Scheduler and Run Configurator | Scheduled priority and approved segment list | Draft Run | Approve narrow segment | Edit or cancel run | Run configuration event |
| Select workflows | Run Configurator | Approved workflow library | One to three workflows | Approve selection | Manual entry | Configuration event |
| Calculate dates | Date Engine | Run date | 12- and 36-month cutoffs | Review run summary | Correct run date with reason | Formula version and values |
| Build source plan | Source Planner | Segment, workflows, source manifests | Planned source types and sources | Approve relevance and coverage | Manual source plan | Source-plan event |
| Create queries | Query Generator | Approved templates and terms | Exact queries | Approve query preview | Edit terms or use manual query | Template and query version |
| Search sources | Source Adapters | Approved query and limits | Candidate Captures | Observe or intervene when required | Manual collection | Adapter attempts and checkpoints |
| Capture evidence | Candidate Engine | Public source content | Candidate record | Approve exact excerpt and meaning | Manual evidence entry | Capture and review events |
| Determine recency | Date Engine | Approved publication date | Recency band | Resolve uncertain date | Context-only status | Calculation event |
| Check first-hand credibility | Review Queue | Candidate and full source | Count, Context, or Reject | Required | Retain as context or reject | Review decision |
| Control duplicates | Duplicate Engine | IDs, URLs, hashes, public labels | Exact flags | Resolve ambiguity | Count conservatively once | Duplicate decision |
| Group Pain Clusters | Cluster Review | Five normalized elements | Cluster membership | Required four-of-five approval | Keep separate | Membership decision |
| Create Lead | Lead Engine | Approved evidence and problem record | Lead | Confirm problem and gap | Keep evidence unpromoted | Lead creation event |
| Strengthen Lead | Query Generator and Review Queue | Validation gaps and opposing templates | New candidates and counterevidence | Approve queries and evidence | Manual search | Query and evidence events |
| Commercial signal | Pattern Flags and Review Queue | Explicit source text | Approved signal or no signal | Required | Leave unconfirmed | Signal decision |
| Competitor check | Verification Adapters | Approved alternatives and official sources | Fact record | Decide gap status | Manual verification | Verification and gap decision |
| Apply gates | Gate Engine | Approved evidence and human decisions | Explicit pass/fail results | Required for judgment gates | Reject or pause | Gate decision |
| Score | Scoring Engine | Human ratings and evidence | Category and total scores | Approve ratings | Return incomplete | Rating and formula event |
| Rank | Ranking Engine | Qualified scorecards | Ranked backlog | Review exceptions | Pause conflict | Ranking event |
| Portfolio treatment | Portfolio Engine | Human standalone/portfolio decision | Linked reserve record | Approve classification | Keep as Lead or reserve | Portfolio decision |
| Capture contact | Contact Review | Explicit public route | Approved Contact Route | Required | Discard route | Contact decision |
| Prepare outreach | Outreach Engine | Approved template fields | Draft | Review exact content | Leave unsent | Draft version |
| Send outreach | Email Adapter or manual browser | Current approved message | Sent state | Per-message approval; manual browser submit | Cancel or retry only as permitted | Approval and delivery event |
| Follow up | Outreach Scheduler | Sent date and response state | Follow-up due | Fresh approval | Cancel | Due and decision event |
| Stop run | Closure Engine | Coverage and reviewed results | Completed, Incomplete, or Failed | Final quality review | Keep open | Closure decision |
| Zero result | Output Engine | No qualified records | Integrity statement | Final review | None; zero remains valid | Run output event |

## 45. Approved Changes From the Manual Workflow

### 45.1 Monthly to Weekly Cadence

- **Exact change:** Replace one larger monthly session with a weekly Monday 10:00 a.m. Eastern scheduled rotation through priorities 1, 2, 3, and 4.
- **Reason:** Reduce the risk of missing opportunities between widely separated market rotations.
- **Risk:** More frequent queued work and operator-review burden.
- **Preserved intent:** One defined segment per run, priority rotation, approval, stopping conditions, and on-demand execution remain.
- **Approval:** Explicitly approved by the user.

### 45.2 Authoritative Storage

- **Exact change:** SQLite becomes authoritative; Google Sheets becomes the synchronized human-facing backlog, reporting, mobile-review, and approval layer.
- **Reason:** Reliable queues, transactions, recovery, state machines, and audit history require stronger local operational state.
- **Risk:** Synchronization conflicts.
- **Preserved intent:** Every manual workbook record remains visible and usable in Google Sheets; protected fields and conflict handling prevent silent divergence.
- **Approval:** Explicitly approved by the user.

### 45.3 Source Collection

- **Exact change:** Repeatable collection may use verified free official access or permitted visible-browser automation.
- **Reason:** Convert manual mechanics into deterministic execution.
- **Risk:** Access rules, page structures, and source capabilities can change.
- **Preserved intent:** Source selection, full-source review, exact provenance, evidence standards, and manual fallback remain.
- **Approval:** Explicitly approved by the user.

### 45.4 Outreach Execution

- **Exact change:** Approved business emails may send automatically; browser-based channels require manual submission.
- **Reason:** Automate a controlled channel while preserving safeguards on higher-friction platforms.
- **Risk:** Accidental or stale outbound communication.
- **Preserved intent:** Per-message approval, honest personalization, one channel, one follow-up, and immediate suppression remain.
- **Approval:** Explicitly approved by the user.

## 46. Final Validation Checklist

Before closing any run, verify:

- [ ] One approved narrow segment was researched.
- [ ] The scheduled priority or on-demand origin is correct.
- [ ] The U.S. and English-language scope was preserved.
- [ ] Excluded industries and trust-barrier markets were removed.
- [ ] Every source used a verified permitted method or manual fallback.
- [ ] No CAPTCHA, access control, robots control, or platform restriction was bypassed.
- [ ] Every exact query and coverage bound was approved and logged.
- [ ] Every counting item is first-hand, dated, specific, and independently attributable.
- [ ] Exact excerpts, URLs, and provenance were saved.
- [ ] Source types were counted by category rather than website.
- [ ] Five independent users support every Qualified Opportunity.
- [ ] At least two source types support every Qualified Opportunity.
- [ ] At least two Evidence Items are from the last 12 months.
- [ ] Older qualifying evidence is no older than 36 months and confirmed current.
- [ ] At least one approved commercial signal exists.
- [ ] Duplicate people, copied complaints, and shared incidents were controlled.
- [ ] Counterevidence and current product reality were reviewed.
- [ ] A light competitor check was completed.
- [ ] Every pass/fail gate was applied before scoring.
- [ ] No failed gate was hidden by a score.
- [ ] Every rating and score is traceable.
- [ ] The exact 100-point weights and tie-break order were applied.
- [ ] Solo build, cost, operation, platform, and data-control requirements passed.
- [ ] Portfolio additions remain secondary.
- [ ] Contact availability did not influence evidence or scoring.
- [ ] Every stored contact route is public, professional, and sourced.
- [ ] No guessing, brokerage, private-data capture, or deanonymization occurred.
- [ ] Every outbound message had current message-specific approval.
- [ ] Browser-channel submission was manual.
- [ ] One-channel and one-follow-up limits were enforced.
- [ ] Replies, rejection, opt-out, failure, and prohibition cancelled follow-ups.
- [ ] Private replies were not treated as public quotations.
- [ ] Raw rejected candidates and inactive contacts follow retention rules.
- [ ] Required coverage and two consecutive no-new-theme batches were completed.
- [ ] Every Lead has a documented validation gap.
- [ ] Every rejection has an explicit reason.
- [ ] Incomplete source coverage is disclosed.
- [ ] Zero qualified results were allowed.
- [ ] SQLite, Sheets, logs, snapshots, and backups are consistent.
- [ ] Every automated decision references its input and governing rule.
- [ ] Final quality control passed.
