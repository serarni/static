# static
Project related to the udacity course Dev-Ops. This is the project 4, build ci/cd pipeline with jenkins

## bucket policy
Here is the bucket policy for the S3. To avoid extra charges into aws bill, I have only allowed my public IP

{
    "Version": "2020-04-11",
    "Id": "PolicyForCloudFrontPrivateContent",
    "Statement": [
        {
            "Sid": "1",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::udacity-cap4-project/*",
            "Condition": {
                "IpAddress": {
                    "aws:SourceIp": "myPublicIp/32"
                }
            }
        }
    ]
}
