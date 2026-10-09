# Agent instructions

## Cloud development environment

Use the Codex cloud environment for this repository. The checkout is at
`/workspace/ModularFleets`; run repository commands from that directory.
Each cloud task already has an isolated environment. Use its existing checkout
and do not create a Git worktree unless the user explicitly requests one.
Do not depend on files or running services on a developer's local machine.

Read `README.md` and `progress.md` before starting work. Inspect the actual
repository and available tools before selecting installation or test commands.
Project files have not yet been provided, so there is currently no established
application stack, dependency installation, build, or test workflow.

Keep secrets in cloud environment settings. Never put credential values in
repository files, setup scripts, logs, or progress notes. Save reusable dependency
installation and service startup instructions in the cloud environment
configuration when the imported project establishes those requirements.

## Branches and agent coordination

- `main`: the shared baseline for reviewed changes.
- `agents/environment`: import the existing project, configure the cloud workflow,
  and validate dependency installation and startup.
- `agents/gameplay`: game rules, simulation, AI, equipment, and balance.
- `agents/ui`: interface, accessibility, and player-facing text.
- `agents/validation`: tests, compatibility, defect investigation, and review.

For additional independent work, create a branch named `agents/<task>` from the
current `main`. Choose a concrete task name and record ownership, scope, and
dependencies in `progress.md`. Reuse an existing branch when its scope matches.
Merge completed work into `main` after reviewing the diff and running the relevant
checks. Do not delete or reset another agent's work.

The source project is the local “Project Game 1” folder at
`/Users/kellan/ChatGPTGame`. It is not mounted in this cloud machine. Import its
source, assets, tests, manifests, lockfiles, documentation, and agent workflow
files when a transfer is available. Preserve the source folder and reconcile its
existing `AGENTS.md`, `README.md`, and `PROGRESS.md` with these bootstrap documents;
do not replace its project history with this initial status record. Keep a single
canonical progress log named `progress.md` for portability across filesystems.

Branches do not isolate files within a shared checkout. Agents working
concurrently on different branches need separate cloud task checkouts. Agents
sharing this checkout must coordinate file ownership and serialize Git writes,
commits, and branch switches. Use parallel agents when requested and when the
tasks have independent scopes; branch creation alone does not start agents.

## Progress and validation

Update `progress.md` with the current branch and task, completed work, actual
validation results, blockers, and the next useful action. Keep cloud setup steps
and working directories explicit. Distinguish local branch creation from remote
publication and saved configuration from a published environment snapshot.

Run the project's documented checks when they become available. Report which
checks actually ran, including failures and skipped checks. Do not claim that the
application is ready based only on a successful dependency installation or a
running process. Preserve existing user changes and avoid unrelated edits.
