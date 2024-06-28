# Apache AWS E-commerce Setup

This guide will help you launch an Ubuntu EC2 instance, clone this repository, and set up an Apache server to serve the files.

## Prerequisites

- AWS account with permission to launch EC2 instances
- SSH key pair for accessing the EC2 instance
- Basic knowledge of command-line operations

## Steps

1. **Launch an Ubuntu EC2 Instance**

   - Log in to your AWS Management Console.
   - Navigate to the EC2 Dashboard.
   - Click on `Launch Instance`.
   - Choose `Ubuntu Server` as the Amazon Machine Image (AMI).
   - Select an instance type (e.g., `t2.micro` for free tier eligibility).
   - Configure instance details, add storage, add tags, and configure security group (allow SSH and HTTP).
   - Review and launch the instance.
   - Select or create a key pair to access the instance.

2. **Connect to Your EC2 Instance**

   - Open your terminal.
   - Connect to your instance using SSH:
     ```bash
     ssh -i /path/to/your-key.pem ubuntu@your-ec2-public-dns
     ```

3. **Clone the Repository**

   - Once connected to the EC2 instance, clone the repository:
     ```bash
     git clone https://github.com/Manojkumar962952/ApacheAwsEcommerce.git
     ```

4. **Install Apache**

   - Update package lists and install Apache:
     ```bash
     sudo apt update
     sudo apt install apache2
     ```

5. **Copy Files to Apache Web Directory**

   - Navigate to the cloned repository and copy the files to the web directory:
     ```bash
     cd ApacheAwsEcommerce
     sudo cp -r * /var/www/html/
     ```

6. **Start Apache**

   - Start the Apache server:
     ```bash
     sudo systemctl start apache2
     ```

7. **Access Your Website**

   - Open a web browser.
   - Paste the public IP address of your EC2 instance into the address bar (e.g., `http://your-ec2-public-ip`).
   - You should see your web application running.

## Troubleshooting

- If you encounter a "Permission denied" error, ensure you are using `sudo` for commands that require elevated privileges.
- If the website does not load, check the status of the Apache service:
  ```bash
  sudo systemctl status apache2


## Demo

![Anon Desktop Demo](./website-demo-image/desktop.png "Desktop Demo")
![Anon Mobile Demo](./website-demo-image/mobile.png "Mobile Demo")

