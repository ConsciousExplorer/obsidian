
1.  The Core Infrastructure (AWS Organizations)
- **Management Account**: Your main central account used for billing and overall control.
- **Dev Account**: A completely isolated environment dedicated to building, experimenting, and testing code safely.
- **Prd (Production) Account**: A strictly locked-down environment where live applications run, entirely separate from development mistakes.

2. The Identity Layer (IAM Identity Center)

- **Single Sign-On (SSO)**: You moved away from risky individual local IAM users and root logins.
- **Centralized Human User**: You created one primary human user identity inside your management account.
- **Access Portal URL**: You now have a unique web dashboard link used as your single front door to log into all your AWS environments.

3. The Access Bridge (Account Assignments)

- **Permission Set**: You defined a blueprint for **AdministratorAccess** (full control).
- **Multi-Account Mapping**: You mapped your central user to that permission set across both the **dev** and **prd** accounts.
- **Temporary Credentials**: When you click an account in your portal, AWS dynamically issues short-lived security tokens behind the scenes, eliminating the threat of stolen, long-term passwords or access keys.

## Github integration


## Terraform Setup
1. Global infrastructure repository to manage individual components
2. Smaller sub repositories that can manage their own infrastructure per repo
3. One large golden-jacket repository using a module approach so that we can keep golden jacket items together