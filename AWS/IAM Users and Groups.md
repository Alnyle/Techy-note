
IAM = Identity and Access Management, Global service
it's where you create users and divide them to groups where each groups has specific `Permissions` defined using policies (e.g., JSON in AWS IAM) that specify allowed or denied actions on specific resources (example delete resource from service or add resource in specific service) . 

IAM is crucial for maintaining **security and governance** in cloud environments.

some point
- Root account created by default, shouldn't be used or shared
- Users are people within your organization, and can be group
- Groups only contain users, not other groups
- Users don't have to belong to a group, and user can belong multiple groups

IAM: Permission
- users and groups permission can be assigned using JSON example
- in another word The policies define the permissions of the users
- In AWS you apply the least privilege principle: `don't give more permission than a user needs`

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Stmt1464034295000",    
      "Effect": "Allow",
      "Action": [
        "s3:AbortMultipartUpload",
        "s3:DeleteObject",
        "s3:ListMultipartUploadParts",
        "s3:PutObject",
        "s3:GetObject"
      ],
      "Resource": [
        "arn:aws:s3:::my_bucket/*"
      ]
    },
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetBucketLocation",
        "s3:ListBucket",
        "s3:ListBucketMultipartUploads"
      ],
      "Resource": [
        "arn:aws:s3:::my_bucket"
      ]
    }
  ]
}    
```
