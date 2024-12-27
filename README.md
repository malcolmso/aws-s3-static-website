# aws-s3-static-website

AWS S3 Static Website

This guide walks you through hosting a static website on AWS S3.
Steps

1. Clone the Repository
Download the index.html and error.html files from the repository:
[aws-s3-static-website](https://github.com/malcolmso/aws-s3-static-website)

3. Create an S3 Bucket
Log in to your AWS Management Console and create a new S3 bucket.

3. Upload HTML Files
Upload the index.html and error.html files to the newly created bucket.

5. Enable Static Website Hosting
-Navigate to the Properties tab of your bucket.
-Scroll down to Static Website Hosting and click Edit.
-Enable static website hosting.
-Enter the following:
-Index Document: index.html
-Error Document: error.html
-Save the changes.
-Note the URL provided in the Bucket Website Endpoint (e.g., http://bucket-##########.s3-website-us-east-1.amazonaws.com/).

6. Update Bucket Permissions
-Go to the Permissions tab in your bucket.
-Under Bucket Policy, click Edit.
-Copy your Bucket ARN (e.g., arn:aws:s3:::bucket-name).
-Use the AWS Policy Generator to create a bucket policy:
-Policy Type: S3 Bucket Policy
-Effect: Allow
-Principal: * (public access)
-Actions: s3:GetObject
-ARN: arn:aws:s3:::bucket-name/*
-Click Add Statement and generate the policy.
-Copy the generated policy and paste it into the Bucket Policy Editor.
-Save the changes.

7. Test the Website

Access the website using the URL provided in the Bucket Website Endpoint.
