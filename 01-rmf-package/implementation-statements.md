# Implementation Statements

**Project:** Logistics Tracking System (LTS)
**Date:** March 2026
**Purpose:** Document how each NIST 800-53 control is implemented using AWS services.

## AC-3 (Access Enforcement)

AWS IAM enforces access control policies for all internal users and processes. IAM roles with least privilege permissions are assigned to EC2 instances and RDS databases. Security groups restrict network access to authorized IP ranges. API Gateway controls external access using API keys, with CloudTrail logging all access attempts for audit.

## SC-7 (Boundary Protection)

API Gateway acts as the external boundary, authenticating all incoming requests before they reach the VPC. Inside the VPC, security groups control traffic to EC2 instances and RDS databases. The VPC is segmented into public and private subnets, with application servers in private subnets that have no direct internet access.

## AU-2 (Event Logging)

CloudTrail monitors and logs system actions. Logs are ingested and analyzed by CloudWatch. EventBridge uses data from CloudWatch Logs and Insights to send SNS messages for specified activity. S3 buckets are used for long term storage.

## SI-4 (System Monitoring)

CloudTrail records all API calls. VPC Flow Logs capture network traffic data. GuardDuty analyzes both to detect indicators of compromise and misuse. CloudWatch monitors GuardDuty findings and triggers SNS alerts for security personnel when threats are detected

## IA-2 (Identification & Authentication)

IAM Identity Center centralizes authentication across the organization's multiple accounts and applications. Identity-based policies enforce least privilege for all IAM users and roles. Resource-based policies control access to S3 buckets containing audit logs. MFA is enforced for all privileged accounts via IAM policy. CloudTrail logs all authentication attempts for audit and accountability.