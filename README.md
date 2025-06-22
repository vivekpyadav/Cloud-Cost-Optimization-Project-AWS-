# EBS Stale Snapshots Cleaner (AWS Lambda Script)

This AWS Lambda function identifies and deletes stale Amazon EBS snapshots to help manage storage costs and maintain a clean AWS environment.

## 🚀 Features

- Scans all EBS snapshots owned by the account.
- Checks if snapshots are associated with:
  - A volume that no longer exists.
  - A volume not attached to any running EC2 instance.
- Deletes stale or orphaned snapshots automatically.

## 📦 Prerequisites

- AWS Lambda with appropriate IAM role permissions:
  - `ec2:DescribeSnapshots`
  - `ec2:DescribeInstances`
  - `ec2:DescribeVolumes`
  - `ec2:DeleteSnapshot`
- Python 3.x runtime
- `boto3` library

## ⚙️ Usage

1. Deploy this script as an AWS Lambda function.
2. Schedule it using Amazon EventBridge (CloudWatch Events) for periodic cleanup.

## 🔒 Disclaimer

Ensure you understand your snapshot retention policy before using this in production. This script deletes snapshots permanently.
