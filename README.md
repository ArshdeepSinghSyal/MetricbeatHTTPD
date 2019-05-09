# ZaloniAssignment

Pre-requisite: The localhost should have pip, boto and ansible installed.

1) Create account on AWS.
    - Create Access Key.
    - Create a SSH key and store the .pem file on your localhost.
    
2) Create instance of a linux machine with the required specifications.
    - Amazon Linux 2 machine selected, with a t2.micro insance (free-tier)
    
3) Create an image (AMI) of the created instance.

4) Create Access Key for aws account and use the values to create environment variables. Gather the AMI-id from the image and put it the ansible script.

5) Run the playbook (.yml file)
    This would create a security group with the specifified details and launch an EC-2 instance.

6) SSH into the virtual machine instance.

7) Install httpd on the linux machine.

8) Install Metricbeat on the linux machine.

9) Configure Metricbeat to monitor httpd on the instance.

10) Restart httpd and metricbeat and view the monitoring logs produced by metricbeat.
