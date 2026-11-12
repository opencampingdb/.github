# Governance

Open Camping DB is run in public on GitHub. Anyone may contribute. Access to the project's repositories, settings and services is given in steps, as people show over time that they can be trusted with it. This page sets out those steps and who decides.

## Roles

| Role | What they can do | How they get it |
|---|---|---|
| Contributor | Open issues and discussions, send pull requests from a fork, review others' pull requests | Anyone, at any time |
| Triager | Label, assign, close and reopen issues and pull requests on one repository. No push access | Asked by the project lead after at least three merged pull requests or a steady record of useful reviews and issue work over two months |
| Maintainer | Review and merge pull requests on one repository, within the protected-branch rules | Asked by the project lead after at least six months as a contributor or triager, and a video call with the project lead |
| Project lead | Owns the organisation, its settings, secrets, deploys and the private `inbox` repository. Decides when there is no agreement | The organisation owner |

Each role is held per repository. Being a maintainer of one repository gives no access to another.

Nobody is given a role because of who they are elsewhere. Experience on other projects is welcome and makes the work go faster, but the steps above still apply. A request for access sooner than this, or pressure to grant it, is declined.

## What stays with the project lead

These are never delegated, at any role:

- Organisation ownership and settings, repository rulesets, and GitHub App installations
- Secrets: Cloudflare, Google and GitHub App keys, salts and app keys
- Deploys of the feedback intake and any other service
- The private `inbox` repository, which holds contributor and owner personal details
- OpenStreetMap and MapRoulette accounts, challenges and their settings. Any change there follows the [Automated Edits code of conduct](https://wiki.openstreetmap.org/wiki/Automated_Edits_code_of_conduct), and the project never edits OpenStreetMap itself.
- Changes to `.github/`, workflows, `CODEOWNERS` and deploy configuration, which `CODEOWNERS` routes to the project lead for review

The organisation keeps one recovery owner besides the project lead, for continuity only. The recovery owner does not use the account for day-to-day work.

## How decisions are made

Most decisions happen on the pull request or issue concerned. A change is merged when a maintainer of that repository (or the project lead) approves it, its checks pass, and nobody with a role on that repository has an open objection.

Changes to the data format, the quality rules, the feedback contract (`SPEC.md`) or anything apps download are announced in an issue at least seven days before they are merged, so app developers can comment.

When people disagree and can't settle it on the issue, the project lead decides, and says why on the issue.

## Security of the project

- Every member of the organisation uses two-factor authentication.
- Helpers are added as outside collaborators on single repositories, not as organisation members.
- The default branch of every repository is protected: pull requests only, a required review, required checks, signed commits and no force pushes.
- Workflows from first-time contributors' pull requests wait for a maintainer's approval before they run.
- Report a security problem privately, with **Report a vulnerability** on the repository's Security tab, never in a public issue. See each repository's `SECURITY.md`.

## Stepping back and removal

Anyone may step back from a role at any time by saying so on an issue or to the project lead. A role unused for six months lapses and can be restored on request.

The project lead removes a role straight away, and without notice, when there is a security concern, a breach of these rules, or harm to contributors or to OpenStreetMap's community. The reason is recorded privately, and publicly where that is safe.

## Changing this page

Changes to this page are made by pull request, open for comment for at least seven days, and merged by the project lead.
