\## AWS Lambda Function to Delete Unused EC2 Snapshots and Volumes This
repository contains an AWS Lambda function designed to automate the
deletion of unused EC2 snapshots and volumes. This helps manage AWS
resources more efficiently and reduce costs by cleaning up resources
associated with terminated EC2 instances.

Prerequisites Before setting up the Lambda function, ensure you have the
following:

An AWS account with the necessary permissions to create Lambda
functions, roles, and policies. An EC2 instance running in your AWS
environment (this will be deleted by the script).

\## Steps to Set Up the Lambda Function

 1. Launch an EC2 Instance Go to the EC2 service in the AWS Management
Console. Launch an EC2 instance.

3. Create a Lambda Function Go to the Lambda service in the AWS
Management Console. Click on Create function. Choose Author from
scratch. -Function name: Give it a descriptive name. -Runtime: Choose
Python 3.x. -Permissions: Choose Create a new role with basic Lambda
permissions. -Click on Create function.

4. Add the Python Script -Scroll down to the Code source section.
-Replace the default code with the Python script provided in this
repository. -Click on Deploy to save your changes.

5. Set Up Permissions

a. Manage Snapshots Permissions -In the Lambda function\'s
configuration, go to General configuration and then Permissions. -Click
on the Role name to open it in a new tab. -In the IAM Management
Console, navigate to the Policies section. Create a new policy: -In the
Filter action, search for DeleteSnapshot and DescribeSnapshots. -Set the
resources to All resources. -Review and create the policy. -Attach this
created policy to the role associated with your Lambda function.

b. Describe Volumes and Instances Permissions -Create another policy in
the IAM Management Console. -From the list dropdown, select
DescribeVolumes and DescribeInstances. -Set the resources to All
resources. -Review and create the policy. -Attach this policy to the
role associated with your Lambda function. 6. Delete the EC2 Instance
-Terminate the EC2 instance that you launched earlier. 7. Run the Lambda
Function -Go back to the Lambda function.

8. Click on Deploy to ensure the latest version of the code is used.
9.Click on Test to execute the function. The function should now delete
snapshots and volumes associated with the terminated EC2 instance.
