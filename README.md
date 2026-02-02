# Policy Sentry (Forked and Extended)

IAM Least Privilege Policy Generator, forked from Salesforce. 
This fork demonstrates generating least-privilege IAM policies using Policy Sentry CRUD mode, including example templates and hybrid cloud RBAC enforcement.

---

## Overview

Writing secure IAM polices by hand can be tedious, error-prone, and time-consuming. Policy Sentry automates the process, generating least-privilege IAM policies scoped by:

- Access Levels: Read, Write, List, Tagging, Permission Management
- Resource ARNs: Resource-specific constraints to minimize over-permission roles

This fork extends Policy Sentry to provide example templates and usage for hybrid cloud scenarios, helping developers and security engineers enforce secure IAM practices efficiently.

**Key Benefits:**

- Automates least-privilege IAM policy creation
- Reduces the risk of over-permissioned roles 
- Demonstrates hybrid cloud RBAC application
- Example templates included for SSM parameters and Secrets Manager secrets

---

## Example

**CRUD Template ('crud.yml'):**

```yaml
mode: crud
name: 'queen2120'
# Specify resource ARNs
read:
- 'arn:aws:ssm:us-east-1:999988883333:parameter/example-parameter'
write:
- 'arn:aws:ssm:us-east-1:999988883333:parameter/example-parameter'
list:
- 'arn:aws:ssm:us-east-1:999988883333:parameter/example-parameter'
tagging:
- 'arn:aws:ssm:us-east-1:999988883333:secret:example-secret'
permissions-management:
- 'arn:aws:ssm:us-east-1:999988883333:secret:example-secret'
# Actions that do not support resource constraints
wildcard-only:
  single-actions: # standalone actions
  - []
  # Service-wide - like 's3' or 'ec2'
  service-read:
  - []
  service-write:
  - []
  service-list:
  - []
  service-tagging:
  - []
  service-permissions-management:
  - []
skip-resource-constraints:
- []
exclude-actions:
- []
  assume-role:
    - []
  assume-role-with-saml:
    - []
  assume-role-with-web-identity:
    - []

---

## My Contribution
- Forked the Salesforce policy_sentry repository
- Demonstrated least-privilege IAM policy generation with example CRUD templates
- Highlighted usage for hybrid cloud RBAC scenarios
- Added clean, resume-ready documentation for GitHub profile visibility

**Impact:** Showcase my ability to automate secure IAM practices and extend open-source tools for cloud security projects.

---

##References
- AWS IAM Actions, Resources, and Condition Keys:https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_actions-resources-contextkeys.html
- Original Policy Sentry repo: https://github.com/salesforce/policy_sentry
- Salesforce Engineering Blog: https://engineering.salesforce.com/salesforce-cloud-security-automating-least-privilege-in-aws-iam-with-policy-sentry-b04fe457b8dc
