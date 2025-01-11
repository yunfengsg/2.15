Answer 1: authorize EC2 to retrieve secrets from AWS Secrets Manager, need an IAM policy that allows the secretsmanager:GetSecretValue action. 
This policy should be attached to the IAM role associated with EC2 instance.
Answer 2: 
1) arn:aws:secretsmanager:ap-southeast-1:255945442255:secret:prod/cart-service/credentials
2) JSON:{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "secretsmanager:GetSecretValue",
      "Resource": "arn:aws:secretsmanager:ap-southeast-1:255945442255:secret:prod/cart-service/credentials:secret:prod/cart-service/credentials"
    }
  ]
}
3)Attach this policy to an IAM Role.
Associate the IAM Role with your EC2 instance
