I analyzed your uploaded PDF and reorganized the content into a cleaner, interview-focused Markdown document. The PDF mainly covers AWS, Kubernetes/EKS, Terraform, CI/CD, Security, Monitoring, and Production Best Practices. 

DevOps & Cloud Interview Notes (Structured Version)

1. AWS EC2 Instance Types

General Purpose

Balanced CPU, Memory, and Networking.

Examples:

- T3, T4g → Burstable workloads, Dev/Test
- M5, M6i, M7g → Web applications, backend servers

Compute Optimized

High CPU workloads.

Examples:

- C5, C6i, C7g

Use Cases:

- CI/CD runners
- Batch processing
- Gaming servers
- ML inference

Memory Optimized

High RAM workloads.

Examples:

- R5, R6i, X2idn

Use Cases:

- MySQL
- PostgreSQL
- Redis
- SAP HANA
- Elasticsearch

Storage Optimized

High local SSD/NVMe throughput.

Examples:

- I3, I4i, D3, H1

Use Cases:

- Kafka
- Cassandra
- Data Warehousing

Accelerated Computing

GPU / AI workloads.

Examples:

- P4, P5 → ML Training
- G4dn, G5 → Graphics and AI Inference
- Inf1, Inf2 → AWS Inferentia

---

2. MySQL Cluster on AWS EC2

Recommended Instances

Production

- R6i / R7i
- Memory Optimized

Cost Optimized

- R6a (AMD)

ARM Based

- R7g (Graviton)

Staging / Small Workloads

- M6i

Storage

GP3

- Standard production workloads

IO2

- High IOPS workloads

High Availability

- Multi-AZ deployment
- Primary + Replica setup
- Separate EC2 instances in different AZs

Backup Strategy

- EBS Snapshots
- Binlog backups
- Point-in-Time Recovery (PITR)

Monitoring

- CloudWatch
- Prometheus
- Grafana
- Slow Query Logs
- Replication Lag Monitoring

Security

- KMS Encryption
- TLS Encryption
- IAM Roles
- Secrets Manager / Vault

---

3. Active Directory to AWS IAM Migration

Recommended Approach

Use:

- AWS IAM Identity Center (SSO)
- AD Connector
- AWS Managed Microsoft AD

Best Practices

- Federated Access
- MFA
- RBAC
- Temporary Credentials (STS)
- Avoid IAM Users

Migration Steps

1. Integrate AD with IAM Identity Center
2. Sync Users and Groups
3. Create Permission Sets
4. Migrate Applications
5. Disable IAM Users

Challenges

- DNS Issues
- Connectivity Issues
- LDAP-based Legacy Applications
- Access Cleanup

---

4. Securing EC2 to S3 Communication

Problem

EC2 instances accessing S3 over the internet.

Solution

Use:

- S3 Gateway VPC Endpoint

Benefits

- No Internet Gateway Required
- No NAT Required
- Private AWS Backbone Connectivity

Security Enhancements

- Block Public S3 Access
- Restrict Bucket Policies
- Enable SSE-KMS
- CloudTrail Logging

---

5. VPC Endpoints

Gateway Endpoint

Supported Services:

- S3
- DynamoDB

Features:

- Route Table Based
- No ENI

Interface Endpoint

Supported Services:

- ECR
- Secrets Manager
- CloudWatch
- SNS
- SSM

Features:

- PrivateLink
- ENI Created

Benefits:

- Private Connectivity
- Compliance
- Reduced Internet Exposure

---

6. AWS Cost Optimization

Governance

- AWS Organizations
- Consolidated Billing

Cost Visibility

- Cost Explorer
- CUR Reports
- AWS Budgets

Shared Services

Centralize:

- Transit Gateway
- Logging
- Monitoring
- AD Services

Optimization Techniques

- Savings Plans
- Reserved Instances
- Rightsizing
- Storage Lifecycle Policies
- Spot Instances

FinOps

- Monthly Cost Reviews
- Chargeback Model
- Cost Center Tagging

---

7. Docker Best Practices

Base Images

Use:

- Alpine
- Distroless
- Slim Variants

Multi-stage Builds

Benefits:

- Smaller Images
- Better Security

Security

- Trivy
- Grype
- Docker Scout

Optimization

- .dockerignore
- Remove Cache
- Use Exact Versions
- Minimize Layers

---

8. Kubernetes / EKS Experience

Core Activities

- EKS Cluster Management
- Helm Charts
- RBAC
- Namespaces
- ConfigMaps
- Secrets
- IRSA

Scaling

- HPA
- Cluster Autoscaler
- Karpenter

Deployments

- Rolling Updates
- Blue-Green
- Canary

Troubleshooting

- CrashLoopBackOff
- ImagePullBackOff
- OOMKilled
- Pending Pods

Monitoring

- Prometheus
- Grafana
- ELK
- CloudWatch

---

9. Kubernetes Auto-Healing

Components

- Kubelet
- Scheduler
- Controller Manager

Pod Failure

- Kubelet restarts containers

Node Failure

- Controller Manager marks node NotReady
- Pods rescheduled automatically

Replica Failure

ReplicaSet ensures desired replica count.

Health Probes

Liveness Probe

Restarts unhealthy containers.

Readiness Probe

Stops traffic to unhealthy pods.

Startup Probe

Handles slow startup applications.

---

10. EKS Traffic Flow

Internet
→ Route53
→ WAF
→ ALB
→ Ingress Controller
→ Kubernetes Service
→ Pod

Benefits

- Centralized Routing
- SSL Termination
- Path-Based Routing
- High Availability

---

11. API Gateway

Use Cases

- API Management
- Authentication
- Throttling
- Versioning

Integrations

- Lambda
- EKS
- ALB

Security

- JWT
- OAuth
- Cognito
- IAM Authorization

---

12. EKS Monitoring

Metrics

- Request Count
- Error Rate
- Latency
- CPU
- Memory

Tools

- Prometheus
- Grafana
- AMP
- AMG

Alerting

- Pod Restarts
- OOMKilled
- High Latency
- High Error Rate

---

13. EKS Logging

Stack

Pods
→ FluentBit
→ OpenSearch / ELK
→ Kibana

Troubleshooting Commands

kubectl logs
kubectl describe pod
kubectl get events

---

14. Secure Database Access from Pods

Best Practices

- Database in Private Subnet
- Security Group Restrictions
- TLS Encryption
- KMS Encryption

Secret Management

- AWS Secrets Manager
- HashiCorp Vault
- External Secrets

Authentication

- IRSA
- IAM DB Authentication

---

15. SSL/TLS in EKS

Common Approach

Certificate stored in ACM.

Flow:

Client
→ HTTPS
→ ALB
→ Ingress
→ Pod

Internal Applications

- cert-manager
- Kubernetes TLS Secrets

Security

- Automatic Renewal
- HTTPS Redirect
- Disable Weak TLS Versions

---

16. Terraform Experience

Resources Managed

- VPC
- EKS
- IAM
- ALB
- Route53
- RDS
- S3

Best Practices

- Modular Design
- Remote State
- Version Pinning
- Code Reviews

Security

- tfsec
- Checkov
- Least Privilege

---

17. Terraform State Management

Remote Backend

- S3 → State Storage
- DynamoDB → State Locking

Benefits

- Team Collaboration
- Versioning
- Backup & Recovery

Recovery

terraform force-unlock LOCK_ID

---

18. CI/CD Pipeline (15 Stages)

1. Checkout Code
2. Install Dependencies
3. Build
4. Unit Tests
5. SonarQube Scan
6. Secret Scan
7. Dependency Scan
8. Docker Build
9. Trivy Scan
10. Push Image
11. Terraform/Helm Validation
12. Deploy to Dev
13. Smoke Tests
14. Approval Gate
15. Production Deployment

---

19. DevSecOps

SAST

Tools:

- SonarQube
- Checkmarx
- Semgrep

DAST

Tools:

- OWASP ZAP
- Burp Suite

SCA

Tools:

- Snyk
- OWASP Dependency Check

Container Security

- Trivy
- Grype

---

20. SonarQube

Checks

- Bugs
- Code Smells
- Vulnerabilities
- Duplicates
- Hardcoded Secrets

Quality Gates

Pipeline fails if:

- Coverage below threshold
- Critical vulnerabilities found
- Excessive code duplication

---

21. Deployment Tools

CI/CD

- Jenkins
- GitHub Actions
- GitLab CI/CD
- Azure DevOps

Kubernetes

- Helm
- ArgoCD
- Kustomize
- kubectl

Infrastructure

- Terraform
- Terragrunt

---

22. Authentication & Authorization

Technologies

- OAuth 2.0
- OIDC
- JWT

Platforms

- Keycloak
- Okta
- Cognito
- Azure AD
- Auth0

Best Practices

- MFA
- Short-Lived Tokens
- Token Rotation
- Least Privilege

---

23. JWT Authentication

Flow

Client
→ Auth Service
→ JWT Token
→ API Gateway / Ingress
→ Microservice

Features

- Access Tokens
- Refresh Tokens
- RBAC
- Claims-Based Authorization

Security

- HTTPS
- RS256 Signing
- Key Rotation
- Short Expiry

Troubleshooting

- Token Expiry
- Invalid Signature
- Audience Mismatch
- Refresh Token Failures

---

Quick Summary for Interviews

Strong Areas

- AWS
- Kubernetes/EKS
- Terraform
- CI/CD
- Docker
- Monitoring
- Security
- DevSecOps
- IAM
- API Gateway

Production Tools

- EKS
- Terraform
- Jenkins
- GitHub Actions
- ArgoCD
- Prometheus
- Grafana
- ELK
- Vault
- AWS Services

Key Real-Time Topics

- Auto Healing
- Blue-Green Deployments
- Canary Releases
- Cost Optimization
- IAM Federation
- VPC Endpoints
- Terraform State Management
- JWT Authentication
- Secure Database ConnectivityThis version is structured like a professional DevOps interview handbook and removes most of the repetition from the original PDF while keeping the important interview points.