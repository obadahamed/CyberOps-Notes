# CLOUD COMPUTING AND THE CLOUD SERVICE MODELS
[[CLOUD COMPUTING AND THE CLOUD SERVICE MODELS]]

| Category | Description | Security Focus |
|--------|-------------|----------------|
| Cloud Computing | Renting IT resources over the internet | Shared responsibility |
| CapEx vs OpEx | Ownership vs Pay-as-you-go | Cost + risk management |
| Public Cloud | Shared infrastructure | IAM, Encryption |
| Private Cloud | Dedicated to one org | Full control, high cost |
| Hybrid Cloud | On-prem + cloud | Secure integration |
| IaaS | Rent infrastructure | OS hardening, patching |
| PaaS | Platform for developers | API security |
| SaaS | Ready software | Access control |
| NIST SP 800-145 | Official cloud definition | Standardization |


---

# Cloud Security Responsibility Model
[[Cloud Security Responsibility Model]]


| Model | CSP Responsibility | Customer Responsibility |
|------|-------------------|-------------------------|
| SaaS | App, OS, Infra, Patching | Users, Access, Data |
| PaaS | OS, Runtime, Infra | Code, APIs, Data |
| IaaS | Physical, Hypervisor | OS, Apps, Network |
| Patch Mgmt | Full (SaaS) | OS & Apps (IaaS) |
| Encryption | Infra level | Keys & Usage |
| Pentesting | Guidelines | Permission & Scope |


---



# DEVOPS, CONTINUOUS INTEGRATION (CI), CONTINUOUS DELIVERY (CD), AND DEVSECOPS
[[DEVOPS, CONTINUOUS INTEGRATION (CI), CONTINUOUS DELIVERY (CD), AND DEVSECOPS]]

| Concept | Description | Security Impact |
|-------|-------------|-----------------|
| Waterfall | Linear development | Late vuln discovery |
| Agile | Iterative development | Early feedback |
| Scrum | Sprint-based framework | Faster fixes |
| DevOps | Dev + Ops integration | Reduced downtime |
| CI | Continuous code merge | Early bug detection |
| CD | Automated deployment | Consistent releases |
| DevSecOps | Security in pipeline | Shift-left security |
| Containers | Packaged apps | Dependency risk |
| Docker | Container runtime | Image scanning |
| Kubernetes | Orchestration | RBAC, Network policies |
| Serverless | CSP-managed compute | Event-based risks |

---


# UNDERSTANDING THE DIFFERENT CLOUD SECURITY THREATS
[[UNDERSTANDING THE DIFFERENT CLOUD SECURITY THREATS]]

| Threat Category     | Examples                       | Impact                   |
| ------------------- | ------------------------------ | ------------------------ |
| Access Risks        | Insider misuse, orphaned admin | Data breach              |
| Compliance Risks    | No certification               | Legal penalties          |
| Multitenancy        | Shared infrastructure flaws    | Data leakage             |
| Encryption Failures | No E2E, weak key mgmt          | Data exposure            |
| Web Attacks         | XSS, CSRF, SQLi                | Account compromise       |
| Identity Attacks    | Session hijacking              | Privilege abuse          |
| Infra Attacks       | Hypervisor, VM escape          | Cross-tenant breach      |
| Network Attacks     | DNS poisoning, MITM            | Traffic interception     |
| API Attacks         | Insecure APIs                  | Data manipulation        |
| DDoS                | Service flooding               | Downtime                 |
| Side-Channel        | Resource leakage               | Sensitive data inference |


