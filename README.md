# ZaloniAssignment

Pre-requisite: The localhost should have pip, boto and ansible installed.

1) Create account on AWS.
    - Create a SSH key and store the .pem file on your localhost.
    
2) Create instance of a linux machine with the required specifications.
    - Amazon Linux machine selected, with 
    
3) Create an image (AMI) of the created instance.

4) Gather the AMI-id from the image and put it the ansible script.

5) Run the playbook (.yml file)
    This would launch a EC-2 micro instance.

6) SSH into the virtual machine instance.

7) Install httpd on the linux machine.

8) Install Metricbeat on the linux machine.

9) Configure Metricbeat to monitor httpd on the instance.

10) View monitoring logs produced by metricbeat.
