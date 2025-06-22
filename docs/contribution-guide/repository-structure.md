# Repository Structure and Navigation

## Understanding and Respecting Existing Repository Patterns

This section outlines the main common structure followed across most repositories. However, it may not reflect every specific folder, naming pattern, or layout used in individual repositories.

Before making structural changes or adding new files:

- Review this documentation to understand the general standards and naming conventions  
- Examine the current structure of the repository you're contributing to. Some details or customizations may not be fully documented but are intentional and consistent within that project  
- Avoid assuming that undocumented areas are unstructured. The existing pattern in a repository should be treated as a valid convention unless otherwise clarified  
- Use this guide as your first reference, and the repository structure itself as a second reference. If you find conflicts between them or are unsure, raise the concern through the appropriate process

If you’re uncertain:

- Use the Community Engagement and Issue Management guidelines to discuss or report inconsistencies, propose improvements, or ask for clarification  
- Do not restructure or introduce new patterns unless you’ve verified that they align with both the guide and the repository’s current practices

This documentation provides a foundation, not an exhaustive list. Contributors are expected to analyze, respect, and follow existing repository conventions when making changes or proposing enhancements.

## Repository Name

Each repository should follow a consistent and descriptive naming convention.

- Repository Name: Use kebab-case and ensure the name reflects the repository’s function or domain  
  Examples: `azure-automation-toolkit`, `terraform-modules-networking`, `github-actions-templates`

The repository name should align with organizational naming conventions. Other naming elements such as application name and CLI format are detailed in the **Naming Conventions and Standards** section.


## Application Repositories

- `/docs`: Contains project documentation  
- `/standards-and-practices`: Includes internal standards, naming conventions, and processes  
- `/technical-guides`: Provides setup, deployment, and usage instructions  
- `/src`: Main source code directory  
  - `/app`: Application-specific code  
  - `/iac`: Infrastructure-as-Code files  
  - `/scripts`: Automation scripts such as `setup.sh`, `destroy.sh`, `backup.sh`  
- `/terraform`: Shared Terraform configuration  
- `/env-override`: Environment-specific overrides  
- `/modules`: Reusable Terraform modules  
- `/environments`: Complete environment configurations with separate entry points


## Terraform Environment Structure

There are two supported approaches for organizing Terraform configurations across environments. Each has its own trade-offs. Choose the one that best fits your infrastructure needs and operational model.

### Approach 1: Centralized Shared Configuration with Overrides

- `/terraform`: Shared Terraform configuration files  
  - `main.tf`: Shared resources configuration across all environments  
  - `variables.tf`: Shared variable definitions  
  - `outputs.tf`: Shared outputs  
  - `provider.tf`: Provider configuration  
  - `versions.tf`: Terraform version constraints

- `/env-override`: Environment-specific variable overrides  
  - `dev.tfvars`: Overrides for the development environment  
  - `staging.tfvars`: Overrides for the staging environment  
  - `prod.tfvars`: Overrides for the production environment

Why use this approach:
- Reuses logic across environments and reduces duplication  
- Easier to maintain and update shared infrastructure  
- Best suited for environments with identical or very similar architecture

Considerations:
- Limited flexibility if environments need to diverge structurally  
- A misconfigured change may affect multiple environments  
- Requires discipline in tfvars usage and isolated execution

### Approach 2: Fully Isolated Environment Configurations

- `/environments`: Environment-specific configurations  
  - `/dev`: Development environment configurations  
    - `main.tf`: Main configuration for the development environment  
    - `terraform.tfvars`: Variable values specific to the development environment  
  - `/staging`: Staging environment configurations  
    - `main.tf`: Main configuration for the staging environment  
    - `terraform.tfvars`: Variable values specific to the staging environment  
  - `/prod`: Production environment configurations  
    - `main.tf`: Main configuration for the production environment  
    - `terraform.tfvars`: Variable values specific to the production environment

Why use this approach:
- Provides full isolation between environments  
- Allows each environment to have custom logic, backends, and resource behavior  
- Ideal for production or environments with different architectures or security needs

Considerations:
- Higher duplication of files  
- Requires a clear process to align shared logic across environments


## Database Repositories

- `/docs`: Documentation related to the database project  
- `/src/db`: Main database source directory  
  - `/schemas`: Table and schema definitions  
  - `/stored-procedures`: Encapsulated business logic  
  - `/functions`: Scalar and table-valued functions  
  - `/views`: Database views  
  - `/triggers`: Insert/update/delete triggers  
  - `/migrations`: Schema versioning and change scripts  
  - `/seed-data`: Initial and test data scripts  
  - `/configs`: Configuration files related to database connections and environment settings  
  - `/indexes`: Index definitions for performance tuning  
  - `/constraints`: Primary keys, foreign keys, and unique constraints


## GitHub Actions Repositories

- `/.github`: GitHub configuration and workflows  
  - `/workflows`: CI/CD workflows (`main.yml`, `test.yml`, `deploy.yml`, etc.)  
  - `/reusable-workflows`: Shared workflows for reuse across projects  
  - `/actions`: Custom GitHub Actions (includes `action.yml`, `Dockerfile`, `entrypoint.sh`)  
  - `/scripts`: Utility shell scripts used in workflows


## Navigation Tips

- Start with the `README.md` or any guide in `docs/technical-guides` for project context and setup instructions  
- Use naming conventions to understand the purpose of each folder  
- Follow existing patterns when adding new files or components  
- Avoid duplication by reusing modules and adhering to structure guidelines


## Benefits of This Structure

### Application Repositories
- **Separation of Concerns**: Clear distinction between application logic, infrastructure, and documentation  
- **Scalability**: Modular layout under `iac`, `modules`, and `environments` supports growth  
- **Maintainability**: Localized directories simplify navigation, debugging, and updates

### Infrastructure as Code (IaC)
- **Modularization**: Shared modules reduce duplication and improve consistency  
- **Environment-Specific Configurations**: Support both override-based and isolated deployments  
- **Automation**: Scripts reduce manual work and enforce best practices during execution

### Database Repositories
- **Clear Organization**: Logical separation of schema, logic, data, and configurations  
- **Version Control and Migrations**: Structured support for schema evolution  
- **Consistency**: Reinforces disciplined and standardized development patterns

### GitHub Actions
- **Organized Workflows**: Workflows, reusable logic, and custom actions are clearly separated  
- **Reusability**: Common processes can be shared across workflows and repositories  
- **Maintainability**: Modular setup simplifies updates and changes  
- **Scalability**: New pipelines and automation tasks can be added without disrupting the existing structure


This structure ensures consistent contribution experiences, supports rapid onboarding, and enables scalable, maintainable growth across all repositories.
