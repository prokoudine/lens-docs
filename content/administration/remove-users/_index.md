---
title: Remove users
weight: 6
type: docs
sidebar:
  open: true
---

This feature is intended for permanently and irreversibly deleting user accounts from your Ondsel Lens instance to comply with users' request.

## What gets redacted

- User fields: email, name, username, password → set to `<REDACTED>`
- Personal organization: name, slug, description → set to `<REDACTED>`
- Username and email become available for new registrations

## What gets deleted

- Default workspace and its root directory
- Default model file (if present)
- Notifications and org secondary references
- Keywords references

## What gets preserved

- User `_id` (record remains with redacted data)
- Subscription details (tier set to `deleted`, state set to `closed`)

## Limitations

- Only works on "mostly empty" accounts
- Fails if user has:
  - Membership in other organizations
  - More than one workspace
  - Files in root directory (other than default model)
  - Subdirectories in root directory
  - Paid subscription (Peer or Enterprise tier)

## How to remove a user

1. Use the [Admin Search](../admin-search) page to find user ID and email address
2. [Open the dashboard](../../dashboard) and click on **Remove User**

![user details](user-details.webp)

3. Enter the **Internal User ID**
4. Enter the **Email Address**
5. Click **Delete** to proceed
6. Review results in the output panel

{{< callout type="important" >}} 
  This action is **not** reversible by design.
{{< /callout >}}
