# Naming Conventions and Standards

## Understanding Naming Conventions and Their Role

Consistent naming is critical to maintaining clarity, readability, and scalability across all repositories. This section documents the most common naming patterns used across our applications, infrastructure, GitHub presence, and command-line tools.

These conventions aim to standardize how entities are named—from files and folders to CLI commands and project identifiers—so contributors can collaborate without confusion or conflicting structures.

While this guide defines the core formats (such as kebab-case, PascalCase, and camelCase), contributors are also expected to align with naming already used in the repository they are working in. If a convention already exists and follows a consistent logic—even if not explicitly documented—it should be preserved.

If you identify a conflict, inconsistency, or opportunity to improve a naming pattern:

- Review this section for general standards  
- Cross-check with what’s already being used  
- Raise the topic using the Community Engagement or Issue Management guidelines before changing established naming styles

This section focuses on consistency and clarity—not enforcing arbitrary rules. When applied correctly, naming conventions reduce onboarding time, support automation, and improve long-term maintainability across diverse systems and teams.


## Kebab Case

**Reference:** [MDN – Kebab Case](https://developer.mozilla.org/en-US/docs/Glossary/Kebab_case)

Kebab case uses lowercase letters with hyphens to separate words (e.g., `project-name`, `user-profile`). It is used across file names, folders, CLI commands, and cloud infrastructure to maintain consistency, improve readability, and prevent casing issues in case-sensitive environments.

**Purpose:**  
To enhance readability, maintain naming uniformity, and ensure compatibility across operating systems, cloud environments, and web URLs.

**Use Cases Relevant to Our Projects:**

- **URLs and Slugs:** Used in clean and SEO-friendly web addresses.  
  _Example: `https://example.com/user-profile/settings`_

- **File Names:** Ensures consistency and clarity across different environments.  
  _Example: `data-fetching-service.js`_

- **Folder Names:** Maintains a predictable structure for directories in both local repos and cloud-hosted filesystems.  
  _Example: `project-assets`, `user-profiles`_

- **Azure Resources:** Azure services like storage accounts, VMs, and resource groups follow this style.  
  _Example: `prod-storage-westus`, `vm-sales-api-001`_

- **GitHub Repository Names:** Repositories are named using kebab-case to ensure consistency across GitHub URLs and automated scripts.  
  _Example: `terraform-modules-networking`, `elmentor-cli`_


## Pascal Case

**Reference:** [Pascal Case – stringcase.org](https://stringcase.org/cases/pascal/)

Pascal Case capitalizes the first letter of every word without spaces or separators (e.g., `UserService`, `AzureAutomationToolkit`). It is used for visual identifiers and public code structures, including naming in object-oriented languages, branding, and display elements.


**Purpose:**  
To provide clarity and uniform formatting for classes, display names, and structural definitions used in programming and user-facing contexts.

**Use Cases Relevant to Our Projects:**

- **GitHub Organization and Display Names:**  
  Used in branding, visual UI, and documentation titles.  
  _Examples:_ `DevOpsVisions`, `Azure Automation Toolkit`

- **Class Names:**  
  Applied to object-oriented programming constructs, particularly in C#, .NET, and TypeScript.  
  _Examples:_ `UserService`, `DataProcessor`, `CommandHandler`

- **Method Names:**  
  Used for public methods that represent actions or behaviors.  
  _Examples:_ `FetchData`, `ResetPassword`, `ValidateInput`

- **Public Properties:**  
  Exposed class properties visible to consumers of the object or API.  
  _Examples:_ `UserName`, `AccountStatus`, `CreatedDate`

- **Interfaces:**  
  Pascal Case prefixed with `I` to distinguish interfaces from concrete classes.  
  _Examples:_ `IUserService`, `ILoggerAdapter`, `IDataProvider`

PascalCase ensures a clear, polished look for all public or user-facing elements in both code and documentation.

## camelCase

**Reference:** [camelCase – MDN Web Docs](https://developer.mozilla.org/en-US/docs/Glossary/Camel_case)

camelCase starts with a lowercase letter and capitalizes the first letter of each subsequent word (e.g., `userName`, `configValue`). It is widely used in programming for internal logic components, offering a clear way to differentiate local and private elements from public ones.

**Purpose:**  
To maintain clarity and provide a standard structure for internal variables, method parameters, and class fields — helping developers distinguish between internal logic and public-facing elements.

**Use Cases Relevant to Our Projects:**

- **Local Variables:**  
  Commonly used for variables declared inside methods or functions.  
  _Examples:_ `orderCount`, `userStatus`, `retryAttempts`

- **Method Parameters:**  
  Parameters passed into functions, helping clarify logic and keep naming consistent with internal naming patterns.  
  _Examples:_ `userName`, `startDate`, `logPath`

- **Private Fields (especially in object-oriented languages):**  
  Used within classes to store data that should not be accessed publicly.  
  _Examples:_ `configValue`, `itemList`, `connectionString`

camelCase is widely supported across JavaScript, TypeScript, Java, C#, and many other languages — and is ideal for elements that are scoped, temporary, or internal.



## Application and Executable Naming

Naming for applications and executables must remain consistent across documentation, help messages, automation scripts, and internal references.

- **Application Name:**  
  A human-readable label used for branding, display, and communication. Usually written in Pascal Case with spaces.  
  _Example: Azure Automation Toolkit_

- **Executable Name:**  
  The official name of the compiled toolkit or CLI executable. It typically follows PascalCase for alignment with branding and visual consistency.  
  _Examples: `AzureAutoKit`, `ElmentorTool`, `ReleaseManagerCLI`_

While PascalCase is preferred for branded tools, kebab-case may still be used for lightweight shell commands or scripts in Unix-style environments.  
_Example (script): `restore-db`, `check-status`_

**Note:**

- PascalCase is recommended for executables when aligning with product or brand names.  
- Kebab-case is typically used for Linux-native or shell-oriented CLI tools where lowercase is standard and scripting-friendly.

The naming must be consistent across CLI usage, help menus, automation examples, documentation, and integration scripts.

## Solution and Project Naming

To maintain a structured and organized codebase, especially in environments using Visual Studio or .NET ecosystems, naming conventions for solution and project files must be clear, consistent, and purposeful.

### Purpose
To clearly distinguish between the overall solution and its individual components, such as APIs, UIs (web, desktop, mobile), CLI tools, libraries, and test projects — improving structure, maintainability, and onboarding for contributors.

### Naming Elements

- **Solution File (`.sln`):**  
  The top-level file representing the complete system or product.  
  _Example:_ `AzureAutoKit.sln`

- **Project Files (`.csproj`, `.fsproj`, etc.):**  
  Each project must reflect its platform, role, or layer using a consistent suffix.

#### Common Project Types and Examples

- **API Project:**  
  _Example:_ `AzureAutoKit.API.csproj`

- **Web Frontend:**  
  _Example:_ `AzureAutoKit.Web.csproj`

- **Desktop Client (WPF, WinForms):**  
  _Example:_ `AzureAutoKit.Desktop.csproj`

- **Mobile Application (MAUI/Xamarin):**  
  _Example:_ `AzureAutoKit.Mobile.csproj`

- **CLI Tool:**  
  _Example:_ `AzureAutoKit.CLI.csproj`

- **Reusable Library:**  
  _Example:_ `AzureAutoKit.Lib.csproj`

- **Unit Test Project:**  
  _Example:_ `AzureAutoKit.Tests.Unit.csproj`

- **Integration Test Project:**  
  _Example:_ `AzureAutoKit.Tests.Integration.csproj`

### Conventions

- All names must use **PascalCase**
- Use **descriptive, role-based suffixes**: `.API`, `.Web`, `.Desktop`, `.Mobile`, `.CLI`, `.Lib`, `.Tests.Unit`, `.Tests.Integration`
- Avoid combining unrelated responsibilities in a single project (e.g., UI and business logic)
- All project files should be referenced in the solution `.sln`
- Organize using **solution folders** (logical grouping), such as `Interfaces`, `Libraries`, `Tests`, `Tools`

### Structure Example

- `AzureAutoKit.sln`  
- `AzureAutoKit.API.csproj` – REST API  
- `AzureAutoKit.Web.csproj` – Web frontend  
- `AzureAutoKit.Desktop.csproj` – Desktop UI  
- `AzureAutoKit.Mobile.csproj` – Mobile app  
- `AzureAutoKit.CLI.csproj` – Command-line interface  
- `AzureAutoKit.Lib.csproj` – Shared business or utility library  
- `AzureAutoKit.Tests.Unit.csproj` – Unit tests  
- `AzureAutoKit.Tests.Integration.csproj` – Integration tests


## Azure Resource Naming Conventions

**Reference:** [Microsoft Azure Resource Naming Best Practices](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-naming)

A consistent and well-structured naming convention for Azure resources helps teams quickly identify the purpose, environment, location, and instance of each resource. This is essential for clarity, automation, and governance across environments.

**Purpose:**  
To ensure each Azure resource name clearly represents its type, function, and deployment context, enabling better tracking, automation, policy enforcement, and cost management.

**Naming Elements:**

- **Resource Type:** Short code identifying the Azure service  
  _Examples: `vm`, `st`, `appsvc`, `sql`, `nsg`, `kv`, `rg`, `pip`, `aks`, `lb`_

- **Workload/Application:** The project, product, or component the resource belongs to  
  _Examples: `webapp`, `api`, `crm`, `salesdata`, `logs`_

- **Environment:** The deployment stage of the resource  
  _Examples: `dev`, `test`, `staging`, `prod`_

- **Azure Region:** The location where the resource is hosted  
  _Examples: `eastus`, `uksouth`, `westeurope`, `centralus`, `southeastasia`_

- **Instance:** A numeric identifier (always numeric)  
  _Examples: `001`, `002`, `003`, `004`, `005`_

**Examples:**

- `vm-crm-prod-uksouth-001` — A production virtual machine for the CRM app in UK South  
- `st-logs-dev-eastus-002` — A dev environment storage account for logs in East US

**Guidelines:**

- Use lowercase and kebab-case formatting  
- Avoid special characters and underscores  
- Always include all five components (or the applicable subset)  
- Use consistent naming across subscriptions, resource groups, and environments  
- Follow Microsoft’s character limits for each Azure resource type


## CLI Command & Parameter Naming (Silent Mode Standards)

To enhance usability and maintain a consistent approach across our toolkits and frameworks, all CLI tools must support **silent mode**. This mode allows commands to be executed without interactive prompts, making them ideal for scripting, automation, and pipelines.

This standard applies to all internal and public-facing CLI tools and includes naming conventions for commands, parameters, help output, and examples

### Command and Method Naming

**Naming Convention:** Commands use kebab-case and avoid spaces or uppercase letters.  
_Examples:_ `add-user`, `remove-user`, `reset-password`  
_Executable:_ PascalCase (e.g., `AzureAutoKit`)

### Parameter Naming

**Naming Convention:** Parameters should follow the kebab case notation and be prefixed with two hyphens (`--`). For commonly used parameters, abbreviated versions are allowed with a single hyphen (`-`).

**Examples:**

- Full: `--user-name`, `--password`, `--email`, `--start-date`  
- Short: `-un`, `-pass`, `-e`, `-sd`, `-ed`, `-o`

### Parameter Descriptions

Each parameter must include a clear and concise explanation in the CLI help output. Descriptions should follow a standard format and include example values.

_Examples:_

- `--user-name`: Full name of the user (e.g., "John Doe")  
- `--password`: User’s password (e.g., "SecurePass123")  
- `--email`: User email (e.g., "mohamed@example.com")  
- `--role`: Assigned role (e.g., "admin")  
- `--output-file`: Path to output file (e.g., `"C:\results\report.txt"`)  
- `--start-date`: Start date in `YYYY-MM-DD` format

### Parameter Format

Values are passed directly after the parameter and quoted if they contain spaces.

```
--user-name "Mohamed Radwan"
--email "mohamed@example.com"
--output-file "C:\results\report.txt"
```

### Help and Usage Output

Each command must support `--help`, listing:

- Command description
- Usage format
- All available parameters and aliases
- Parameter descriptions
- At least one real usage example

**Example Output:**
```
Description:
Adds a new user to the system with full user profile.

Usage:
AzureAutoKit add-user [options]

Options:
--user-name, -un       Full name of the user (e.g., "Mohamed Radwan")
--password, -pass      Password (e.g., "SecurePass123")
--email, -e            Email address (e.g., "john@example.com")
--role, -r             Role (e.g., "admin", "editor")
--department, -d       Department (e.g., "IT", "Sales") [optional]
--start-date, -sd      Start date (YYYY-MM-DD)
--end-date, -ed        End date (YYYY-MM-DD)
--output-file, -o      File to write results to
--help                 Show this help and exit
```


### Examples

**Add Admin User:**
```
AzureAutoKit add-user --user-name "Mohamed Radwan" --password "SecurePass123" --email "johndoe@example.com" --role "admin"
```

**Generate Report to File:**
```
AzureAutoKit generate-report --start-date "2024-09-01" --end-date "2024-09-30" --output-file "C:\reports\summary.txt"
```

**Using Short Parameters:**
```
AzureAutoKit add-user -un "Mohamed Radwan" -pass "SecurePass123" -e "mohamed@example.com" -r "admin"
```


By adopting these naming standards, we ensure that all CLI tools are:

- Consistent across frameworks  
- Easy to use and automate  
- Compatible with help systems and scripts  
- Maintainable across all platforms and contributors


## GitHub Organization and Project Naming

Consistent naming across your GitHub organization and projects improves professionalism, discoverability, automation integration, and collaboration. This section defines how we name the organization, repositories, and GitHub Projects (the visual project boards).

### Purpose

To establish a clear and recognizable structure for repositories and project boards across GitHub, making it easier for contributors and stakeholders to navigate and align with branding and automation workflows.

### GitHub Organization

- **Organization Name (Display):**  
  The official display name used for the GitHub organization.  
  _Format:_ Pascal Case with spaces  
  _Example:_ `DevOps Visions`

- **Organization URL:**  
  The GitHub URL for the organization must use PascalCase without spaces (for brand consistency).  
  _Format:_ PascalCase  
  _Example:_ `https://github.com/DevOpsVisions`

### Repository Naming

- **Repository Name (URL):**  
  All repository URLs must follow **kebab-case**, using lowercase and hyphens for separation.  
  _Example:_ `azure-automation-toolkit`, `elmentor-cli`, `terraform-modules-networking`

- **Repository Folder Display Name:**  
  In documentation or automation tooling, the folder or title representing the repo may use Pascal Case with spaces for better readability.  
  _Example:_ `Azure Automation Toolkit`

This ensures that:
- Repository URLs are consistent with scripts and automation pipelines
- Repository display names align with branding and human readability

### GitHub Project Naming (Project Boards)

- **Project Board Title:**  
  The project title must match the repository name but use Pascal Case with spaces.  
  _Example:_ For repo `azure-automation-toolkit`, the project board should be named `Azure Automation Toolkit`

- **Use Case:**  
  This naming convention ensures the board title is clear for humans, while the underlying repository and automation continue using kebab-case.
