# my-skills

This repository maintains reusable Agent Skills and harness-neutral instruction prompts for coding agents.
Skills define task-specific workflows. Prompts define persistent defaults for how an agent works and communicates.

## Contents

| Resource | Purpose | Maintenance |
| --- | --- | --- |
| [three-loop-workflow](skills/three-loop-workflow) | Plan, implement, verify, and review software changes at a depth suited to their risk | Independent [repository](https://github.com/caohaotiantian/three-loop-workflow), pinned here as a Git submodule |
| [orchestrate](skills/orchestrate) | Choose direct or delegated execution, coordinate subagents, and own integrated acceptance | Independent [repository](https://github.com/caohaotiantian/orchestrate), pinned here as a Git submodule |
| [Global instructions](prompts/AGENTS.md) | Set defaults for workflow selection, verification, development tools, response style, and visuals | Maintained directly in this repository |

The skills complement each other: `orchestrate` owns coordination, while `three-loop-workflow` owns implementation depth and evidence.
The global prompt asks agents to apply both automatically when relevant.
The prompt does not depend on a particular harness configuration format, but its named skills, tools, and capabilities must be available or adapted to the target environment.

## Clone

```sh
git clone --recurse-submodules https://github.com/caohaotiantian/my-skills.git
cd my-skills
```

For an existing clone, initialize the submodules at their recorded versions:

```sh
git submodule update --init --recursive
```

## Install

These steps apply whether a person or an agent performs the installation.
Choose the target harness's skill discovery directory and instruction-file location using its documentation.
This repository does not prescribe harness-specific paths or configuration.

### 1. Install the skills

After cloning and initializing the submodules, copy each desired package directory into the target skill discovery directory.
Use the inner package directory, not the submodule repository root:

| Skill | Package directory to copy |
| --- | --- |
| `three-loop-workflow` | [`skills/three-loop-workflow/three-loop-workflow/`](skills/three-loop-workflow/three-loop-workflow) |
| `orchestrate` | [`skills/orchestrate/orchestrate/`](skills/orchestrate/orchestrate) |

Copy the complete package, including its references and other bundled files.
Copying only `SKILL.md` breaks access to supporting resources.
The destination should have this shape:

```text
<skill-directory>/
  three-loop-workflow/
    SKILL.md
    references/
    ...
  orchestrate/
    SKILL.md
    references/
    ...
```

If a destination package already exists, back it up outside the skill discovery directory before replacing it.
Replace the old package rather than overlaying files, so obsolete resources do not survive an update.

### 2. Install the global instructions

Read [`prompts/AGENTS.md`](prompts/AGENTS.md) before adopting it.
It contains personal defaults, including automatic workflow selection and a preference for `uv` for Python.
Install the referenced skills if you want to use those workflow defaults unchanged.

Back up any existing instructions at the intended destination.
Copy the prompt into the harness's supported global or project instruction location, using the filename it expects.
If that location already contains instructions you need, merge the relevant sections instead of replacing them blindly.
Resolve conflicts with existing rules and adapt unavailable tools or capabilities explicitly.

The repository-root [`AGENTS.md`](AGENTS.md) governs work on this repository; it is not the installable global prompt.
Installing skills or instructions does not grant tools, permissions, or subagent capabilities.

### 3. Verify the installation

Start a new session or reload instructions using the harness's documented mechanism.
Confirm that it discovers the installed skills and loads the intended instruction file.
Ask the agent to read an installed skill and one of its bundled references to check that the package layout is intact.
Then use a small, non-destructive task to check workflow selection against the installed instructions.
Do not treat copying files alone as proof that the harness loaded them.

## Update an installation

Pull this repository, then restore the skill versions recorded by the collection:

```sh
git pull
git submodule update --init --recursive
```

Review the prompt and skill changes before applying them.
Replace installed packages using the same backup and verification steps as the initial installation.
Reconcile local prompt customizations with `prompts/AGENTS.md`.
Pulling this repository does not update separately installed copies.

## Update skill versions

For collection maintainers, fetch the latest version from each skill repository's configured upstream branch:

```sh
git submodule update --remote --recursive
git diff --submodule=log
```

Review the changes. Then commit the updated version references:

```sh
git add skills/three-loop-workflow skills/orchestrate
git commit -m "Update skill versions"
git push
```

Before you edit a submodule, switch to a working branch inside it. Commit and push changes to the skill repository first. Then update the version reference in this repository.

## Add a skill

Replace `<skill-name>` with the repository name:

```sh
git submodule add https://github.com/caohaotiantian/<skill-name>.git skills/<skill-name>
```

Update the skill index above. Commit `.gitmodules`, the new submodule path, and this README. The commit history records skill additions and version changes.

## Maintain prompts

Edit reusable instruction prompts under `prompts/`.
Keep `prompts/AGENTS.md` independent of harness-specific configuration paths and preserve its distinction from the repository-root instructions.
Review changes for conflicts with the referenced skills.
Update the contents table when adding a prompt.
Apply accepted changes to installed copies separately; this repository does not synchronize local harness configuration.

## Agent records

[AGENTS.md](AGENTS.md) defines entry reads and the project record lifecycle.
[MEMORY.md](MEMORY.md#read-selector) selects conditional project context.
Local `.agent/` directories contain task records and evidence. Their existence does not require reading them.

## Project language

Use English for project content unless another language is explicitly requested.
