# System Description

**System Name:** Logistics Tracking System (LTS)

**System Purpose:** Provides real-time tracking and documentation of high-value assets in transit using AWS cloud services with redundant storage and automated audit trails.

**Data Types Handled:** Shipment manifests (CUI), customer PII (CUI), asset tracking data, real-time location updates, delivery confirmation records.

**System Location:** AWS GovCloud (us-gov-west-1)

**Users:** Logistics coordinators, security officers, program managers, and external researchers with approved access.

**System Boundary:** EC2 application servers, RDS database, S3 storage for manifests, VPC with public and private subnets, API Gateway for external partner integration, CloudTrail for audit logging.

**Impact Level:** Moderate (based on CUI data types handled)
