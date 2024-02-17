# cloud-resume-challenge
Using my resume and website to create a cloud resume




To deploy code from your GitHub repository to an Amazon S3 bucket, you have a few options. Let’s explore them:

## DeployHQ:
DeployHQ is a service that streamlines the deployment process. Here’s how you can set it up:
Create a new project in DeployHQ, specifying your GitHub repository.
Connect to your GitHub repository by logging in and selecting the repository.
Configure your S3 Bucket by providing the bucket name, access key ID, secret, and path prefix (usually a directory like “htdocs” or “public_html”).
Deploy for the first time to get started.
DeployHQ will automatically handle subsequent deployments when you push changes to your repository1.

# Git Remote S3:
If you prefer command-line tools, you can use git-remote-s3. Here’s how:
Add the S3 bucket as a remote: git remote add s3remote s3://my_bucket/prefix.
Push or pull to/from the remote as usual: git pull s3remote master or git push s3remote.
You can even clone from S3: git clone s3://my_bucket/prefix2.

# Git S3 Push:
Another option is git-s3-push:
Clone the repository and navigate to the repo root.
Build the binary using go build cmd/git-s3-push.go.
Alternatively, you can use go run cmd/git-s3-push.go without building3.

# AWS CodeBuild:
Create a webhook from GitHub to CodeBuild.
Whenever you push changes to GitHub, CodeBuild starts a container.
In CodeBuild, you can use tools like boto3 (Python) or aws-cli to interact with your S3 bucket and upload artifacts4.
Remember that the actual cost depends on your specific usage, such as the number of deployments, data transfer, and storage in your S3 bucket. Be sure to check the pricing details for both GitHub and Amazon S3 to estimate the cost accurately. Happy deploying! 🚀
