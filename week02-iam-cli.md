# Week 2: IAM and AWS CLI Investigation

## HarborTech Ticket Summary

TKT-2026-0002 is about Marcus Webb not being able to access the Riverside Goods inventory bucket. Marcus can sign in to AWS, but he gets an `AccessDenied` message when he tries to access the `riverside-inventory` bucket. His job requires him to view inventory reports and upload approved inventory files.

## Client Impact

Marcus cannot complete his inventory work because he does not have the permissions he needs. He can sign in, but he cannot access the S3 bucket or perform his required tasks.

## AWS Services Involved

The main AWS services and concepts involved are:

* IAM
* IAM users, groups, roles, and policies
* Amazon S3
* AWS CloudShell
* AWS CLI
* AWS Regions

IAM controls who can access AWS resources and what they are allowed to do. S3 is the service storing the inventory files.

## Virtualization Connection

Cloud resources such as virtual machines, storage, and networks are managed through software. IAM permissions control who can manage these resources. A user may have permission to use one resource but not another, depending on their assigned permissions.

## Evidence Reviewed

I reviewed the following evidence:

* Marcus can successfully sign in to AWS.
* Marcus is an Inventory Coordinator.
* He needs to list the inventory bucket, read inventory reports, and upload approved files.
* His IAM user has no job-function group listed.
* His IAM user has no directly attached permission policy listed.
* His request to list the bucket returns `AccessDenied`.
* The client proposed using `AmazonS3FullAccess`.
* `aws sts get-caller-identity` showed the identity being used in CloudShell.
* `aws iam get-role --role-name LabRole` showed the LabRole and its trust relationship.
* `aws iam list-attached-role-policies --role-name LabRole` showed four attached policies.
* `aws iam list-role-policies --role-name LabRole` showed no inline policies.

## Operational Analysis

The problem is authorization, not authentication. Marcus can sign in, which proves that his credentials work. The `AccessDenied` message shows that he does not have permission to perform the requested S3 action.

The evidence also shows that Marcus does not have a listed group or directly attached permission policy. This supports the finding that he is missing the permissions needed for his job.

## Recommendation

Marcus should receive only the S3 permissions needed for his job. He needs to list the `riverside-inventory` bucket, read the required inventory files, and upload approved files.

`AmazonS3FullAccess` is too broad because it gives access to S3 resources beyond what Marcus needs. The permissions should be limited to the Riverside Goods inventory bucket and the required actions.

## Escalation Notes

The finding is that Marcus can authenticate but does not have the required authorization. The recommended direction is to provide limited S3 permissions for his inventory work.

An authorized HarborTech team member should review and make the production IAM change. As an intern, I should document the evidence, recommend the least-privilege approach, and escalate the change instead of making the production change myself.

## Lessons Learned

This week I learned that authentication and authorization are different. Authentication confirms who a user is, while authorization controls what the user can access. I also learned how to use AWS CLI commands to investigate IAM information and how least privilege can limit access to only what a user needs.

## Professional Vocabulary

* **Authentication:** Verifying who a user is.
* **Authorization:** Determining what a user is allowed to access.
* **IAM:** AWS service used to manage identities and permissions.
* **Policy:** Rules that allow or deny access to AWS resources.
* **Least Privilege:** Giving a user only the access they need.
* **AccessDenied:** An error showing that the current identity does not have permission for an action.
* **AWS CLI:** A command-line tool used to work with AWS.
* **CloudShell:** A browser-based command-line environment in AWS.
* **Caller Identity:** The AWS identity making the current request.
* **Resource Scope:** The specific resource that a permission applies to.
