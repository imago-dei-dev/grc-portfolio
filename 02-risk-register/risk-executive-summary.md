# LTS Risk Assessment - Executive Summary

I ran a risk assessment on the Logistics Tracking System (LTS) using NIST 800-30. Found 12 risks total. Most are manageable. One needs attention now.

## The Numbers

- High risk (17-20): 1
- Medium-High (15-16): 1  
- Medium (10-14): 9
- Low (1-9): 1

## The One That Keeps Me Up at Night

**R-004 - Terminated credentials not being removed.** Score 20.

People leave the company but their accounts stay active. Someone could exploit this. Fix is simple: run IAM credential report quarterly and kill stale accounts. Q2 2026.

## Other Notable Risks

- **R-008 (Score 16)** - Prime contractors don't tell subs what CUI is. Nothing we can do but accept it. Reassess yearly.

- **R-005 (Score 15)** - No breach response plan. Who calls who? No one knows. Need to document this.

- **R-009 (Score 15)** - Some of our stuff is in commercial AWS regions, not GovCloud. That's a problem for CUI. Need to migrate.

- **R-010 (Score 15)** - One of our vendors runs on the clear web. Unencrypted drives, HTTP traffic. Replace them or force FedRAMP compliance.

## Heatmap Quick Look

High risk (R-004) is top right corner. Most medium risks cluster in the middle. Only one low risk.

No critical risks. System is not a dumpster fire.

## What I Recommend

| When | What |
|------|------|
| Q2 2026 | Kill stale credentials, write IR plan, draft SSP |
| Q3 2026 | Migrate to GovCloud, fix the bad vendor |

## Bottom Line

Fix the credential thing first. Everything else can wait a quarter. System is safe enough to run but has compliance gaps.
