# Data Breach Proof of Concept (POC) - Dummy Environment

> **DISCLAIMER:**  
> This repository is strictly for **educational and testing purposes** (e.g., verifying secret scanners, testing Data Loss Prevention (DLP) tools, or running security pipeline demonstrations).  
> **All keys, tokens, names, and credentials below are 100% fake and randomly generated.** Do not commit production credentials or real personally identifiable information (PII) to version control.

---

## Overview

This repository demonstrates synthetic data structures that simulate accidental exposure of sensitive assets. Security tools and DLP engines should detect and flag these dummy patterns during static analysis or automated CI/CD scans.

---

## 1. Mock API Keys & Credentials

Below are example formats of common secret leaks using non-functional, synthetic tokens:

* **AWS Access Key ID:** `AKIAIOSFODNN7EXAMPLE`
* **AWS Secret Access Key:** `wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY`
* **Generic API Token:** `sk_live_51NxEXAMPLE0000000000000000000000000000000000`
* **GitHub Personal Access Token (PAT):** `ghp_000000000000000000000000000000000000`
* **Private Key Sample:**
  ```text
  -----BEGIN RSA PRIVATE KEY-----
  MIIEowIBAAKCAQEA0Z1gFAKEKEYEXAMPLE1234567890abcdefghijklmnopqrstuv
  wxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890abcdefghijklmnopqrstuvwx
  yzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890abcdefghijklmnopqrstuvwx
  -----END RSA PRIVATE KEY-----
  ```

---

## 2. Sample Synthetic PII

Below is synthetic personally identifiable information (PII) modeled for DLP parser testing.

| ID | Full Name | Email | Phone Number | Mock Credit Card (Luhn-Valid Test) |
|---|---|---|---|---|
| `USR-101` | Jane Doe | `jane.doe@example.com` | `+1-555-019-2831` | `4532-0000-0000-0000` |
| `USR-102` | John Smith | `john.smith@example.net` | `+1-555-014-9982` | `5412-8800-0000-0000` |
| `USR-103` | Alex Rivera | `arivera@example.org` | `+1-555-017-4401` | `3782-820000-00000` |

---

## 3. Mock Database Connection String

```text
postgres://app_user:SuperSecretPassword123!@localhost:5432/production_db?sslmode=disable
```

---

## Testing & Verification Steps

1. Run your scanner (e.g., `gitleaks`, `trufflehog`, or internal DLP software) against this repository.
2. Ensure alerts are triggered for:
   - High-entropy strings / API key patterns
   - Unencrypted connection strings containing passwords
   - Credit card / PII regex patterns
3. Confirm that alert workflows route notifications to your incident response team or dashboard.
