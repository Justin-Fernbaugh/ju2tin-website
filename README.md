# Ju2tin Website hosted at https://ju2tin.com
This repository contains the source code for my personal website, hosted on AWS using S3, CloudFront, and Amplify. The website was set up using the following steps in AWS:

Host a static website using Amazon S3
Add a custom domain managed by Amazon Route 53
## Setup
The steps taken to set up the website using the above guides are explained below:

## Step 1: Host a static website using Amazon S3
### Create an Amazon S3 bucket: 
Created a new S3 bucket to store the website's static files. The bucket name is the same as the custom domain, e.g., www.example.com.

### Enable static website hosting: 
Configured the S3 bucket to function as a static website by enabling the "Static website hosting" feature in the bucket properties. Set the index document to index.html and the error document to error.html.

### Upload files to the S3 bucket: 
Uploaded the website's static files, including index.html, error.html, and any other assets such as images, CSS, and JavaScript files, to the S3 bucket.

### Set bucket policy: 
Configured the S3 bucket's policy to allow public access to the files. This is required for users to access the website over the internet.

## Step 2: Add a custom domain managed by Amazon Route 53
Register a custom domain: Registered a custom domain using Amazon Route 53. If the domain was registered elsewhere, transferred the domain to Route 53.

### Create a CloudFront distribution: 
Created a new Amazon CloudFront distribution to serve the static content from the S3 bucket. Configured the distribution settings, such as the origin domain name (the S3 bucket) and the default root object (index.html).

### Configure SSL/TLS: 
Requested an SSL/TLS certificate from AWS Certificate Manager (ACM) to enable HTTPS for the website. Associated the certificate with the CloudFront distribution.

### Create a Route 53 alias record: 
Created an alias record in the Route 53 hosted zone for the custom domain. Set the alias target to the CloudFront distribution's domain name.

### Configure AWS Amplify: 
Connected the GitHub repository to AWS Amplify and configured the build settings to automatically deploy changes to the website when the repository is updated.

## Usage
To make changes to the website, clone the repository, make updates, and push the changes back to the repository. AWS Amplify will automatically detect the changes and deploy the updated website.

