# EC2-Apache-Deployment
1. Launch an EC2 Instance:

Begin by logging into the AWS Management Console and navigate to the EC2 service.
Choose an Amazon Machine Image (AMI) that suits your needs. A free tier eligible option like Amazon Linux 2 is a good starting point.
Select an appropriate instance type. t2.micro is a free tier option for low traffic websites.
Configure the instance details including network settings, storage, and security group. Here, create a security group that allows inbound HTTP traffic on port 80 (default for web traffic) for the world (0.0.0.0/0) or a specific IP range if you prefer more restricted access.

2. Install Apache Web Server:

There are two main approaches to install Apache:

Direct Installation: Connect to your EC2 instance using SSH and run commands to update system packages and install Apache. You can leverage user data scripts during launch to automate this process.
Pre-configured AMI: Alternatively, you can create a custom AMI with Apache pre-installed. This 
simplifies future deployments with identical configurations.

3. Configure Apache:

By default, Apache serves content from the /var/www/html directory. You'll place your website files here.
You can configure virtual hosts to serve different websites from the same instance if needed.

4. Upload Website Files:

Securely transfer your website files (HTML, CSS, JavaScript, etc.) to the /var/www/html directory on your EC2 instance. Tools like SCP or S3 buckets can be used for this purpose.

5. Test and Launch:

Once the files are uploaded, restart the Apache service using the appropriate command (e.g., sudo systemctl restart httpd on Amazon Linux).
Access your website using the Public DNS address of your EC2 instance in a web browser.
