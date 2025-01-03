AWS Cloud Cost Optimization - Identifying Stale EBS Snapshots

This project aims to optimize AWS cloud storage costs by identifying and deleting stale EBS snapshots that are no longer associated with any active EC2 instances. By running a Lambda function with appropriate permissions, you can automate the cleanup of unnecessary snapshots to reduce storage expenses.

Overview

The Lambda function:

Fetches all EBS snapshots owned by your account ('self').

Retrieves a list of active EC2 instances (both running and stopped).

Checks if the snapshots are associated with any active volumes or instances.

Deletes stale snapshots that are not associated with any active EC2 instances or volumes.

Steps to Reproduce

1. Create an EC2 Instance and Take a Snapshot

Create an EC2 instance and attach a volume.

Take a snapshot of the attached volume.

2. Set Up the Lambda Function

Create a Lambda function using the provided Python code.

Ensure the function has necessary IAM permissions to describe and delete snapshots, instances, and volumes.

3. Execute the Lambda Function

Run the Lambda function to identify and delete stale EBS snapshots.

4. Delete the EC2 Instance and Volume

Terminate the EC2 instance and delete the associated volume.

5. Run the Lambda Function Again

Re-execute the Lambda function to delete any remaining stale snapshots.

Python Code

The full Python code for the Lambda function is included in the ebs_stale_snapshosts.py file in this repository.

Key AWS Services Used

EC2 (Elastic Compute Cloud)

EBS (Elastic Block Store)

AWS Lambda

IAM (Identity and Access Management)

Benefits

Cost Optimization: Automatically deletes unnecessary EBS snapshots to reduce AWS storage costs.

Automation: Leverages AWS Lambda to automate the identification and deletion of stale snapshots.

Security: Ensures IAM roles and permissions are properly configured to prevent unauthorized actions.
