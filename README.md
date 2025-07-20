# 🛡️ Terraform AWS Sentinel Policies

This repository contains a curated set of **Sentinel policies** designed to enforce compliance, governance, and security best practices for **Terraform Cloud deployments on AWS**.

## 📌 Purpose

Use this repo to:

- Enforce **AWS Foundational Security Best Practices** and **CIS Benchmarks**
- Prevent configuration drift and non-compliant infrastructure
- Support team collaboration using **Policy-as-Code**
- Integrate with **Terraform Cloud** using version control or manual upload

---


## 🔐 Sentinel Policy Categories

| Category           | Description                                                 |
|--------------------|-------------------------------------------------------------|
| 🔒 IAM             | Prevent overly permissive policies (`*` actions)            |
| 🧱 EC2             | Enforce approved instance types                             |
| 🪣 S3              | Require bucket encryption and versioning                    |
| 🔐 VPC             | Enforce flow logs and subnet tagging                        |
| 🔐 RDS             | Ensure encryption at rest and in-transit                    |

---

## ⚙️ sentinel.hcl Example

```hcl
policy "aws_instance_type" {
  enforcement_level = "hard-mandatory"
}

policy "s3_encryption" {
  enforcement_level = "soft-mandatory"
}

policy "iam_no_star_policy" {
  enforcement_level = "hard-mandatory"
}



Enforcement levels:

advisory: Warn only

soft-mandatory: Block applies, but can override

hard-mandatory: Block applies with no override


