# Control Selection Rationale

**System:** Logistics Tracking System (LTS)
**Date:** March 2026

## Selected Controls

**AC-3 (Access Enforcement):** Setting controls for who has access to the system is a high priority, since LTS deals with CUI and PII.

**SC-7 (Boundary Protection):** LTS gives external partners access to its API endpoints, which is the boundary to the rest of the system and must be properly controlled.

**AU-2 (Audit Events):** Logs are needed to detect and investigate incidents. All compliance frameworks require this.

**SI-4 (System Monitoring):** Monitoring is standard in compliance. GuardDuty is constantly scanning logs from the perimeter and internally for alerts to send notifications about.

**IA-2 (Identification & Authentication):** Each user, employee or contractor, must use unique credentials. Shared accounts defeat controls which have been implemented for accountability.

## Controls Not Selected

I didn't pick controls like CP-9 (backup) and PE-3 (physical access) because those are either inherited from AWS GovCloud or handled by someone else's policy. The five controls above are the ones the LTS team actually controls and can be assessed at our system boundary.