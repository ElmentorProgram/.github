# Commit Guidelines

Clear and consistent commit messages improve the readability of the project history, simplify code reviews, enable automated tooling, and help trace bugs and changes effectively.

This section defines the structure, action verbs, and patterns we follow across all commits.

## Commit Message Format and Structure

We follow a standardized format for all commit messages:

```
<type>(<optional-scope>): <short, imperative summary>

<optional-body with explanation or context>

<optional-footer with references or issue IDs>
```

- The **type** describes the kind of change (see below)
- The **scope** is optional and refers to a specific module or component
- The **summary** is written in the **imperative mood** (e.g., "fix bug", not "fixed" or "fixes")
- The **body** explains what and why, not how
- The **footer** can include references like `Fixes #123` or `Related to #456`

## Naming Conventions and Action Verbs

### Allowed Types (prefix keywords):

- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation only changes
- `style`: Formatting, missing semi colons, etc.; no code change
- `refactor`: Code change that neither fixes a bug nor adds a feature
- `perf`: Performance improvements
- `test`: Adding missing tests or correcting existing tests
- `chore`: Other changes that don’t modify src or test files
- `ci`: CI/CD configuration or automation changes
- `build`: Changes to build system, infrastructure, tooling

### Common Scopes (if applicable):

- `cli`, `infra`, `db`, `api`, `ui`, `tests`, `auth`, `docs`, etc.

### Approved Action Verbs (for summaries):

- `add`, `fix`, `update`, `remove`, `rename`, `refactor`, `document`, `optimize`, `validate`, `improve`, `migrate`, `deprecate`

Examples:

- `fix(api): handle null token response`
- `docs(readme): clarify setup instructions`
- `refactor(cli): extract user input logic into function`
- `build: update GitHub Actions cache strategy`

## Examples and Templates

### Basic Feature Commit

```
feat: add support for user profile picture upload
```

### Commit with Scope and Body

```
fix(cli): handle empty input crash

This prevents the CLI from throwing an exception when no argument is passed.
Added a default fallback with a clear message.

Fixes: #341
```

### Chore or Cleanup Commit

```
chore: remove legacy logging module
```

### Template for All Commits

```
<type>(<scope>): <summary>

<body - explain what changed and why>

<footer - references, e.g. Fixes #123>
```

## Best Practices

- Use **present-tense**, imperative style in summaries  
  - "fix bug" not "fixed bug"  
  - "add docs" not "adding docs"
- Keep the summary under **72 characters**
- Separate summary from body with a blank line
- Reference issues in the **footer**, not in the summary

## Multi-Project Repositories (Monorepos)

If you're working in a repository with multiple components (e.g., CLI + Infra + Docs), always use a **scope** for clarity:

- `feat(cli): add interactive user prompt`
- `fix(iac): correct subnet mask`

## Automation Support

This structure is compatible with [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) and enables:

- **Changelog generation** using tools like `standard-version`
- **Semantic versioning** with `semantic-release`
- **Commit linting** (optional: via Husky + commitlint)
- **Pull request title and changelog enforcement**
