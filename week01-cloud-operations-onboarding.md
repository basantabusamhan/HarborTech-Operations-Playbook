Week 1: Cloud Operations Onboarding
HarborTech Ticket Summary

Ticket ONB-2026-0001 is a Week 1 environment readiness review for HarborTech. The purpose of the ticket was to verify that the required AWS training environment could be accessed and used correctly. The review included AWS Academy access, Learner Lab access, the permitted Region, IAM restrictions, session behavior, budget rules, Reset behavior, AWS documentation access, and Playbook readiness.

Client Impact

Environment readiness is important because an intern needs to have access to the required tools before beginning client support work. Understanding the environment boundaries also helps prevent mistakes, unexpected costs, or actions that are not allowed. Completing these checks first allows support work to begin with a clear understanding of what can and cannot be done.

AWS Services Involved

The onboarding review involved AWS Academy and the AWS Learner Lab environment. AWS IAM was reviewed to understand permission restrictions. The confirmed Region was us-west-2, which is one of the permitted Regions. The AWS account is a sandbox environment with specific service, permission, and cost limits. Official AWS documentation was also reviewed as a resource for learning and verifying AWS operations.

Virtualization Connection

Cloud infrastructure uses virtualization to abstract physical hardware such as servers and storage. This allows users to work with virtual resources without directly managing the physical hardware. However, virtualization does not remove operational responsibilities. Cloud operations still require managing account access, Regions, permissions, security, configurations, costs, and platform restrictions.

Evidence Reviewed

The following readiness evidence was reviewed:

AWS Academy Cloud Operations access was confirmed.
Learner Lab access was successfully confirmed.
The lab was started successfully.
The confirmed Region was us-west-2.
The Learner Lab Readme was reviewed.
IAM restrictions were identified.
The LabRole IAM role was identified as a pre-created role.
The LabInstanceProfile was identified as a pre-created instance profile.
Session behavior and the session timer were reviewed.
Budget reporting behavior was reviewed.
The budget display was identified as delayed by approximately 8 to 12 hours.
Reset behavior was reviewed.
The AWS CLI Command Reference was located as an official AWS documentation resource.
The HarborTech Operations Playbook requirements were reviewed.

Operational Analysis

The evidence shows that the AWS training environment is accessible and that the required onboarding checks can be completed. The us-west-2 Region is permitted by the Learner Lab rules. The inability to create IAM users or groups is an expected permission restriction and not evidence of a platform failure.

The session and budget information also show that cloud operations require active cost management. The budget display may not reflect recent activity because it can take 8 to 12 hours to update. Resources should therefore be stopped or deleted when they are no longer needed instead of waiting for the budget display to change.

These are verified findings based on the Learner Lab Readme. An assumption should not be treated as evidence, so any future access or technical issue should be verified before deciding that the platform has failed.

Recommendation

The environment is ready for Week 2 support work based on the readiness checks completed. No additional AWS resources should be created for the Week 1 review. The next step is to continue following the Learner Lab permissions, Region restrictions, budget rules, and documentation practices during future work.

Escalation Notes

No unresolved access or environment issue was identified during the readiness review. The IAM restriction preventing the creation of users and groups is an expected Learner Lab boundary and does not require escalation.

If an issue occurs in the future that is not explained by the Learner Lab restrictions, it should be documented with the available evidence and escalated to the instructor rather than bypassing the restriction.

Lessons Learned

Week 1 showed me that cloud operations readiness is more than simply being able to log into AWS. I learned that I need to verify permissions, Regions, session behavior, costs, and environment rules before performing technical work. I also learned that official documentation is an important resource when researching AWS services and commands.

Another important lesson was to separate verified findings from assumptions. If something does not work, I should first check the environment rules and documentation before deciding that there is a platform problem. This helps prevent unnecessary changes and supports better operational decisions.

Professional Vocabulary

Virtualization: A technology that allows physical computing resources to be represented and used as virtual resources.
Evidence: Information that can be used to support and verify an observation or conclusion.
Finding: A conclusion based on information or evidence that was reviewed.
Assumption: Something believed to be true without enough evidence to verify it.
Escalation: Reporting an unresolved issue to the appropriate person or team for further assistance.
Sandbox: A controlled environment where users can practice and test without having unrestricted access to production systems.
Region: A geographic area where AWS provides cloud services and resources.
IAM: AWS Identity and Access Management, which controls access to AWS resources and services.
Operations Playbook: A documented collection of procedures, evidence, lessons, and operational guidance used to support consistent work.
