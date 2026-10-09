# ModularFleets

Repository: `KrusherG/ModularFleets`.

Development uses the Codex cloud environment with this checkout at
`/workspace/ModularFleets`. Read `AGENTS.md` for agent coordination and
`progress.md` for the current status.

The repository currently contains the collaboration instructions and progress
record. The existing project is in `/Users/kellan/ChatGPTGame` on the local
computer (Codex project “Project Game 1”). That folder must be transferred to the
cloud checkout before application setup can be verified. No application files,
dependency manifests, or test commands are available in this checkout yet.

## Branch workflow

`main` holds the shared baseline. Agent lanes are `agents/environment` for import
and cloud setup, `agents/gameplay` for game systems, `agents/ui` for the interface,
and `agents/validation` for tests and review. Add `agents/<task>` branches as
independent tasks arise; use separate cloud task checkouts for simultaneous work
on different branches.

## Cloud startup

```sh
cd /workspace/ModularFleets
git status --short --branch
git branch --list
```

Inspect the current branch and preserve any existing changes before switching
branches. Follow the project-specific setup and validation commands once the
project has been imported and those commands have been verified.
