---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "infisical_projects Data Source - infisical"
subcategory: ""
description: |-
  Fetches the list of projects.
---

# infisical_projects (Data Source)

Fetches the list of projects.

## Example Usage

```terraform
terraform {
  required_providers {
    infisical = {
      source = "infisical/infisical"
      version = "0.1"
    }
  }
}

provider "infisical" {
  api_key  = "YOUR_API_KEY"
  host     = "https://infisical.com"
}

# List all organizations for the user's api_key.
data "infisical_organizations" "all" {}

data "infisical_projects" "all" {
  organization_id = data.infisical_organizations.all.organizations[0].id
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `organization_id` (String) Identifier of the organization.

### Read-Only

- `id` (String) Current Unix timestamp for id.
- `projects` (Attributes List) List of projects. (see [below for nested schema](#nestedatt--projects))

<a id="nestedatt--projects"></a>
### Nested Schema for `projects`

Read-Only:

- `environments` (Attributes List) List of environments. (see [below for nested schema](#nestedatt--projects--environments))
- `id` (String) Identifier of the project.
- `name` (String) Name of the project.

<a id="nestedatt--projects--environments"></a>
### Nested Schema for `projects.environments`

Read-Only:

- `id` (String) Identifier of the environment.
- `name` (String) Name of the environment.
- `slug` (String) Slug of the environment.


