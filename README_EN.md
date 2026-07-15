[中文](README.md) | [English](README_EN.md)

# Liang's Skill Bag

> A personal collection of Skills for OpenClaw and agent workflows, covering development productivity, memory, research, automation, document processing, frontend design, and related tasks.

## Repository Scope

This repository is a collection, not a single software product with one installation method, quality standard, or license. Its top level contains more than 100 Skills or related projects, and individual directories may use different structures, dependencies, configuration methods, and upstream versions.

Only the repository-level documentation is maintained in Chinese and English. Child `README` files, `SKILL.md` files, and other documents retain their original language and upstream content; they are not being translated or rewritten in bulk.

## Contents and Sources

The current collection mainly draws from these channels:

| Source | Description |
| --- | --- |
| Personal installation and curation | Skills used in an OpenClaw workspace or installed through ClawHub. |
| Superpowers / agent workflows | Skills related to agent-assisted development workflows. |
| OpenClaw built-in or ecosystem content | Skills collected from the OpenClaw npm package or its ecosystem. |
| Other third-party projects | Some directories retain their own documentation, metadata, or license files. |

These sources have not yet received a consistent directory-by-directory audit. The root-level [`良哥skill目录.docx`](良哥skill目录.docx) is an existing inventory artifact, but it may not reflect the repository's current state; use the Git tree as the source of truth.

## Usage

Before installing anything, enter the target directory and read its `SKILL.md`, `README`, scripts, and dependency instructions in full. Confirm the source and requested permissions, then copy only the selected Skill into your local OpenClaw Skills directory.

macOS / Linux example:

```bash
cp -R <skill-name> ~/.openclaw/workspace/skills/
```

Windows PowerShell example:

```powershell
Copy-Item -Recurse .\<skill-name> "$HOME\.openclaw\workspace\skills\"
```

These are common path examples only; follow your own OpenClaw configuration. Do not install the entire repository at once, and do not run unreviewed scripts.

## Security Review

A Skill may execute local commands, access files, use the network, control a browser, or connect to third-party services. At minimum, review:

- The behavior, tools, and permissions declared in `SKILL.md`.
- Scripts, dependencies, and configuration for destructive operations, external downloads, or unknown endpoints.
- Whether API keys, tokens, accounts, or other credentials are required. Keep credentials in the local environment or a dedicated secret store, never in this repository.
- Whether the Skill's source, version, and license permit your intended use or redistribution.
- Whether the first run can be tested in an isolated environment or with a low-privilege account.

Inclusion is not a security endorsement, and the repository does not claim that every item has passed a code audit. Manually confirm every step for Skills that can delete files, operate accounts, send messages, make payments, or publish content.

## Third-Party Licensing

There is currently no repository-wide license, and one license cannot be assumed to cover every child directory. Some third-party directories include their own license or provenance information, while others may have incomplete licensing records. Before using, modifying, or sharing a Skill, follow the terms in its directory and upstream project. When no explicit license exists, do not assume permission to copy, modify, or redistribute it.

## Gitlink Limitations

`claude-mem` and `web-access` are stored as gitlink entries, but this repository currently has no `.gitmodules` mapping. A normal `git clone` will therefore not retrieve their actual contents, and `git submodule update` cannot reconstruct them from this repository alone.

If you need either project, first verify its trusted upstream URL and referenced commit, then obtain it separately. Do not treat an empty path or unresolved gitlink as a complete Skill.

## Maintenance Recommendations

- Record the upstream URL, version or commit, license, and review date when adding or updating a Skill.
- Clearly separate personal modifications from original upstream content for easier upgrades and traceability.
- Periodically check for broken dependencies, dangerous permissions, and abandoned projects.
- Never commit API keys, tokens, passwords, chat logs, or other private data.
