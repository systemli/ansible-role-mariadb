# AGENTS.md

Ansible role that installs and configures MariaDB on Debian (bookworm, trixie), including optional replication.

## Layout

- `defaults/main.yml`: all role variables with defaults
- `tasks/`: `main.yml` and `replication.yml` (included from `main.yml`)
- `handlers/`, `templates/`, `meta/main.yml`: handlers, config templates, Galaxy metadata
- `molecule/default/`: integration test (Docker, Debian 13)
- `requirements.yml`: collection dependencies (`ansible.mysql`)

## Checks

- `ansible-lint` must pass with the default configuration (no config file)
- `molecule test` runs the role in a container; CI runs it on Debian 12 and 13 via `systemli/github-ansible-workflow`
- If you run `ansible-lint`, it creates `.ansible/`; it is git ignored, never commit it

## Conventions

- Use fully qualified module names (`ansible.builtin.*`) and `true`/`false` booleans
- Give every task a `name`
- New or changed role variables need an entry in `defaults/main.yml` and the README
- GitHub Actions are pinned to commit SHAs with a `# vX.Y.Z` comment; Dependabot updates them

## Commits and PRs

- Write in English, use conventional commit titles (`feat:`, `fix:`, `chore:`, `ci:`; `!` for breaking changes)
- The PR title sets the release-drafter label (`enhancement`, `bug`, `chore`, `breaking`); a breaking change bumps the major version
- Open PRs as draft and fill in `.github/pull_request_template.md`: what changed and why, plus a breaking changes section if needed
- Do not list changed files or claim test results in the description; CI covers that
