# my-skills

Track the Agent Skills that I develop and maintain. Each skill has an independent repository. This repository records specific versions through Git submodules.

## Skills

| Skill | Purpose | Repository |
| --- | --- | --- |
| [three-loop-workflow](skills/three-loop-workflow) | A three-stage software development workflow | [caohaotiantian/three-loop-workflow](https://github.com/caohaotiantian/three-loop-workflow) |
| [orchestrate](skills/orchestrate) | Subagent orchestration and final acceptance | [caohaotiantian/orchestrate](https://github.com/caohaotiantian/orchestrate) |

## Clone

```sh
git clone --recurse-submodules https://github.com/caohaotiantian/my-skills.git
cd my-skills
```

For an existing clone, initialize the submodules at their recorded versions:

```sh
git submodule update --init --recursive
```

## Update skill versions

Fetch the latest version from each skill repository's default branch:

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

## Project language

Use English for project content unless another language is explicitly requested.
