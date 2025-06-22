# Branching Strategy

A clear and consistent branching strategy ensures efficient collaboration, streamlined code review, minimal merge conflicts, and a reliable deployment pipeline.

This section outlines how contributors should fork, branch, name branches, and interact with key branches like `main`, `dev`, and feature branches.

## Forking and Branching

All contributors — whether external community members or internal participants — **must fork the repository and submit Pull Requests (PRs) from their fork**. This process ensures traceability, control, and separation of unverified code changes.

Only **specifically approved internal team members**, as explicitly listed or internally announced by name or role (e.g., `Lead Group Advisory`, `Executive`), may create branches directly inside the main repository. Even then, they **must strictly follow the branch naming conventions and contribution workflow** like all other contributors.

General branching guidelines:

- Always create a new branch from the appropriate base (`main` or `dev`)
- Never commit directly to `main` or `dev` unless explicitly permitted
- Use **feature branches** for enhancements or new capabilities
- Use **hotfix branches** for urgent patches to production
- Use **release branches** when preparing formal builds for deployment

## Branch Naming Convention

Branch names must follow **kebab-case** and begin with a keyword that reflects the type of work.

**Format:**  
`<type>/<short-description>`

**Allowed Types:**

- `feature` – New features or enhancements
- `fix` – Bug fixes
- `hotfix` – Emergency production fixes
- `chore` – Non-functional changes like dependency updates or refactoring
- `docs` – Documentation updates
- `test` – Changes related to tests

**Examples:**

- `feature/add-user-onboarding`
- `fix/email-validation-error`
- `hotfix/api-auth-crash`
- `chore/update-terraform-modules`
- `docs/improve-readme`
- `test/add-integration-tests-for-q2a`

## Main, Development, Feature, Hotfix Flow

- **main**  
  The production branch. Only tested, stable code is merged here. No direct commits. Releases are finalized here via PRs or formal release branches.

- **dev**  
  The active development branch. All feature and fix branches must be merged here first. Periodically integrated into `main` during release cycles.

- **feature/**  
  Temporary branches for building new features. Created from `dev`, merged back into `dev` once complete and reviewed.

- **fix/**  
  Used for addressing bugs or defects. Also created from and merged into `dev`.

- **hotfix/**  
  Critical patches that need immediate deployment. Created from `main`, then merged back into both `main` and `dev`.

- **release/** (optional)  
  Used for preparing formal releases. Supports stabilization, final testing, and documentation updates. Merged into both `main` and `dev`.

## Mainline Practices: GitHub Flow and Release Flow

In certain projects — especially those requiring faster turnaround or simplified release cycles — we support **mainline development models**. These strategies reduce overhead, minimize complexity, and enable rapid value delivery.

### Mainline Branching Practices

Mainline development (also known as trunk-based development) encourages teams to integrate continuously into the `main` branch. All branches are short-lived, created only for small, isolated changes or for a few developers to collaborate on a focused task.

This strategy minimizes long-lived branches, avoids reverse integration, and supports modern DevOps automation workflows.

### GitHub Flow

GitHub Flow is a streamlined, fast, and widely adopted model ideal for most projects — especially tools, microservices, websites, and documentation.

**Key Principles:**

- All work is done in short-lived feature branches
- Each feature branch opens a pull request targeting `main`
- Pull requests are reviewed and automatically validated with tests
- Once approved, changes are merged and immediately deployed (if automation is in place)

**Best Practices for GitHub Flow:**

- Implement **automated tests** (unit, integration, etc.) to validate every pull request  
- Use **continuous deployment** to eliminate manual handoffs  
- Leverage **observability and monitoring** to detect and resolve issues early  
- Avoid reverse integration — all changes flow forward, reducing risk

**Ideal For:**

- Projects that ship frequently or continuously
- Teams focused on simplicity and speed
- Repos that don’t require supporting multiple versions in parallel

### Release Flow (Microsoft Standard)

For teams managing multiple live versions or requiring stability in production environments, **Release Flow** extends GitHub Flow to accommodate formal release branches.

**Key Characteristics:**

- All work is merged into `main` continuously  
- When preparing a release, a new version branch is created (e.g., `release/1.2`)  
- Bug fixes are made directly in `main`  
- Fixes are **cherry-picked into release branches** as needed to maintain production versions

**Why Use Release Flow:**

- Keeps `main` moving forward without interruption  
- Avoids regressions by fixing issues in `main` first  
- Maintains control over production releases without duplicating workflows  
- Eliminates the need for risky reverse integration

**Ideal For:**

- Products with long upgrade cycles or staggered deployments
- Enterprise software with multiple active release versions
- Teams using external versioning and needing parallel support streams

### Keep It Simple, Keep It Fast

Branching strategies should **enable delivery**, not delay it.

- Want to ship continuously? → Use **GitHub Flow**  
- Need to support multiple releases in production? → Use **Release Flow**

Avoid promoting branches through environments — this often introduces unnecessary risk and complexity. **Reverse integration** (merging changes backward) should be avoided in favor of forward-flowing, clean, and automated delivery practices.

> The best branching model is the one that gets in the way the least.  
> **Stop promoting branches. Start delivering value.**
