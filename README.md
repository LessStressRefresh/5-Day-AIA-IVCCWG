# 5-Day-AIA-IVCCWG
Intensive Vibe Coding Course With Google

Note Propmpts are encapsulated between "---"

Main File: Ticket-Reviewer-Agent
Additional File: Local Agent_V1 Reference file for the Agent running using the Antigravity CLI

Problem:
larger Companies or individuals would require validaiton against tickets, With the increase of digital tickets validation options may be limited.

Solution:
An AI agent that allowes for conditions to be stipulated and conditions to be reviewed allowes for a safe review process, This provides reporting and safe guards to be put in place. 

###
Index:
###

1. Antigravity CLI Installation & Configuration
System Installation & Path Setup

Installation on macOS, Linux, and Windows (PowerShell & CMD).

Initial launch (agy) and Google OAuth account authentication.

Tool Permission Architecture

Understanding security vs. velocity configurations via /config.

request-review: Default collaborative mode pausing for user approval on external modifications.

proceed-in-sandbox: Autonomous execution inside isolated, virtualized containers.

always-proceed: Full autonomous mode executing directly on the host machine.

strict: Zero-trust mode restricting the agent to read-only tools.

2. Environment & Toolchain Setup
Google Cloud Environment Initialization

Linking to Google Cloud Projects, setting regional targets, and enabling core generative platform APIs (aiplatform, cloudtrace, cloudbuild, agentregistry).

ADK Skill Set Integration

Installing the agents-cli toolchain to supply the agent with API references, project scaffolding templates, and evaluation workflows.

Local Workspace Provisioning

Creating workspace directories, configuring local Git identities, and initializing Python virtual environments using uv.

3. ADK Agent Project Scaffolding
Age Reviewer Agent Blueprint

Generative scaffolding for an ADK 2.0 movie house ticket review workflow.

Integration of in-memory stores tracking user IDs, age thresholds, and guardian requirements.

Production Best Practices: Concurrency Control

Addressing race conditions and double-redemption vulnerabilities in shared memory states.

Architectural overview of pessimistic locking (.with_for_update()) vs. optimistic versioning.

Graph Linting & Syntax Validation

Running syntax and static analysis over structural agent workflows.

4. Secure Coding Standards & Gating
Persistent Context Management (CONTEXT.md)

Strict enforcement of Pydantic schemas for tool input validation.

Elimination of unauthorized raw shell execution.

Mandatory pre-commit remediation loops.

Static Analysis & Pre-Commit Enforcement

Custom Semgrep configuration targeting hardcoded API credentials.

Pre-commit hook setup blocking unsafe commits via explicit exit codes (--error).

Runtime Interception Hooks (hooks.json)

Configuring PreToolUse event handlers with mandatory validation matchers to safely filter shell commands.

5. Threat Modeling & TDD Guardrails
STRIDE Assessment Skill

Automated mapping of system boundaries, entry points, and data persistence.

Evaluating the six security pillars: Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privilege.

Compilation of a structured workspace threat_model.md.

Test-Driven Development (TDD) Gates

Enforcing mandatory "Security Boundaries & Assertions" documentation during task planning phases.

6. Runtime Deployment & Validation
Local Architecture Prototyping

Configuring decision graphs containing deterministic routing (auto_approve nodes vs. human-in-the-loop RequestInput pauses).

Dependency Management & Packaging

Python dependency locking and pre-deployment dry runs.

Agent Runtime Operations

Deploying builds to live execution environments.

Verification testing via simulated programmatic payloads.

7. Frontend Dashboard Development & Cloud Run Deployment
FastAPI Service Architecture

Interface generation utilizing modern design patterns (glassmorphism typography, smooth transitions).

State polling endpoints querying the ADK Vertex AI Session Service for unresolved interrupts.

Session-resumption POST handlers interacting with the SDK.

Cloud Run Deployment Orchestration

Containerized deployment with environment-variable injected metadata.

Managing public access control and IAM runtime service account permissions.

8. Pub/Sub Event Pipeline Integration
Messaging Topology Creation

Setting up explicit ingestion streams and auxiliary dead-letter storage queues.

Push Subscription Wiring

Provisioning authenticated invocation accounts (pubsub-invoker).

Creating raw push endpoints (--push-no-wrapper) targeted directly at Agent Runtime REST APIs.

Tuning acknowledgment deadlines and fallback retry limits.

9. End-to-End System Testing & Infrastructure Decommissioning
Live Pipeline Execution

Simulating event ingest for automated flows and human-gated runtime flags.

Resource Cleanup Lifecycle

Orderly removal of Cloud Run services, Pub/Sub channels, subscriptions, and associated service identity accounts using quiet execution modes.
