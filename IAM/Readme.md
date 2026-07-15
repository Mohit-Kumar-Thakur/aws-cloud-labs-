# AWS IAM - User Creation & Permission Management

> Hands-on implementation of AWS Identity and Access Management (IAM) focusing on secure user creation, permission assignment, and access management.

---

## Overview

This project demonstrates the practical implementation of AWS Identity and Access Management (IAM) by creating an IAM user with console access and assigning permissions using AWS Managed Policies.

The objective is to understand how AWS authenticates users, authorizes access to AWS resources, and enforces security through identity-based access control.

---

## Services Used

| Service | Purpose |
|---------|---------|
| AWS IAM | Identity and Access Management |

---

## Objectives

- Create an IAM User
- Configure AWS Console Access
- Set a Custom Password
- Assign Permissions using AWS Managed Policies
- Add Resource Tags
- Review User Configuration
- Verify Successful User Creation

---

## Implementation Workflow

```text
AWS Console
      │
      ▼
Open IAM Dashboard
      │
      ▼
Create IAM User
      │
      ▼
Configure Console Login
      │
      ▼
Assign Managed Policy
      │
      ▼
Add Tags
      │
      ▼
Review Configuration
      │
      ▼
Create User
```

---

## Practical Implementation

### Step 1 — Open AWS IAM Console

Navigate to the IAM Dashboard from the AWS Management Console.

---

### Step 2 — Create a New IAM User

Configure

- User Name
- Console Access
- Custom Password

---

### Step 3 — Assign Permissions

Attach an AWS Managed Policy to grant access.

Policy Used

```
AmazonS3FullAccess
```

---

### Step 4 — Add Tags

Example

| Key | Value |
|-----|-------|
| practice_user | practice |

Tags help organize and identify AWS resources.

---

### Step 5 — Review Configuration

Verify

- User Details
- Password Type
- Attached Policy
- Tags

---

### Step 6 — Create User

AWS generates

- IAM User
- Console Login URL
- Temporary Credentials

---

## Screenshots

### IAM Dashboard

> `screenshots/dashboard.png`

![IAM Dashboard](screenshots/dashboard.png)

---

### Create User

> `screenshots/create-user.png`

![Create User](screenshots/create-user.png)

---

### Permission Assignment

> `screenshots/permissions.png`

![Permissions](screenshots/permissions.png)

---

### Review Configuration

> `screenshots/review.png`

![Review](screenshots/review.png)

---

## Concepts Covered

- IAM
- Authentication
- Authorization
- IAM User
- Managed Policies
- Console Access
- Resource Tags
- Least Privilege Principle

---

## Best Practices

- Never use the Root User for daily operations.
- Enable MFA for every privileged account.
- Follow the Principle of Least Privilege.
- Prefer IAM Roles over long-term credentials.
- Use descriptive resource tags.
- Rotate credentials periodically.
- Regularly review IAM permissions.

---

## Key Takeaways

- IAM is a Global AWS Service.
- Every AWS user should have only the permissions required to perform their tasks.
- AWS Managed Policies simplify permission management.
- Tags improve resource organization.
- Console access enables secure sign-in to AWS resources.

---

## References

- AWS IAM Documentation
- AWS Security Best Practices

---

## Repository Structure

```text
IAM/
│
├── README.md
├── screenshots/
│   ├── 01-dashboard.png
│   ├── 02-create-user.png
│   ├── 03-permissions.png
│   └── 04-review.png
```

---

> **Note:** All sensitive information (Account ID, Sign-in URL, Usernames, Passwords, and any confidential identifiers) has been removed or masked before publishing the screenshots.


## Screenshots

### Custom Customer Managed Policy

![Custom Policy](screenshots/custom_policy.png)

---

### IAM User Groups

![IAM User Groups](screenshots/IAM_user_groups.png)

---

### IAM Users

![IAM Users](screenshots/IAM_users.png)

---

### IAM Access Advisor

![IAM Access Advisor](screenshots/IAM_Access Advisor.png)

---

### IAM Policy Simulator

![IAM Policy Simulator](screenshots/IAM_policy_simulator.png)

---

### Developer User - Bucket Listing Permission Denied

This demonstrates that the custom IAM policy does **not** grant the `s3:ListAllMyBuckets` permission.

![Developer List Permission Denied](screenshots/developer_list_permission_denied.png)

---

### Updated Custom Policy

The custom IAM policy was updated by granting the required `ListAllMyBuckets` permission.

![Updated Policy](screenshots/Screenshot 2026-07-15 193642.png)

---

### Bucket Listing After Policy Update

After updating the custom policy, the developer user was able to list S3 buckets successfully.

![Bucket List Success](screenshots/developer_list_permission_removed.png)

---

### Bucket Creation

A new Amazon S3 bucket was created to validate the permissions assigned through the custom IAM policy.

![Bucket Created](screenshots/developer_create_bucket.png)

---

### Object Upload

Successfully uploaded an object to the Amazon S3 bucket using the developer IAM user.

![Object Upload](screenshots/developer_put_object.png)

---

### Delete Object Permission Test

The developer user attempted to delete an object. The operation was restricted according to the custom policy, demonstrating permission enforcement.

![Delete Object](screenshots/developer_delete_object.png)
