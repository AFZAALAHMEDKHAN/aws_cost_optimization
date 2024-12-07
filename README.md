# AWS Cost Management by Identifying and Removing Unused Resources

# Problem:
Developers often create EC2 instances with attached volumes for backup purposes. Alongside these, snapshots are also created for backup. However, when an EC2 instance is terminated, developers sometimes overlook deleting its corresponding snapshots. This leads to continued costs for unused snapshots, even though they are no longer necessary.

# Solution:
To optimize storage costs, we developed a smart AWS Lambda function that monitors snapshots and EC2 instances. The Lambda function identifies and deletes any snapshots that are no longer attached to active EC2 instances. This proactive approach helps eliminate unnecessary expenses and ensures efficient cost management.

# Other Use Cases:

1. Elastic IP Costs: Developers may attach an Elastic IP to an EC2 instance but forget to remove it after termination. The unused Elastic IP continues to incur costs until it is explicitly released.

2. Unused RDS Instances: Database instances like Amazon RDS can be launched but left running even when they are no longer needed. These idle instances result in ongoing costs unless explicitly terminated.

3. Unutilized S3 Buckets: S3 buckets created for temporary storage or backups may remain in place without any real purpose, leading to storage costs. Monitoring and deleting these unutilized buckets can save costs.

4. Orphaned Load Balancers: Load balancers can be created but may remain active even after their associated resources are terminated. These orphaned load balancers continue to incur costs, which can be avoided by regular monitoring and cleanup.

5. Detached EBS Volumes: EBS volumes can remain attached to snapshots or EC2 instances but become orphaned after the parent EC2 instance is terminated. These volumes often incur storage costs unless cleaned up.

By addressing these common issues, AWS costs can be managed more effectively, ensuring resources are only used when necessary.
