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
    This would create a security group with the specifified details and launch an EC-2 instance of the specified image id.
    
    ```ansible-playbook -i ./hosts ec2.yml```

6) SSH into the virtual machine instance.

    ```ssh -i ./my-key.pem ec2-user@ec2-18-219-213-110.us-east-2.compute.amazonaws.com```
    
7) Install httpd on the linux machine.
    
    ```sudo yum install httpd```
    
8) Install Metricbeat on the linux machine.

    ```curl -L -O https://artifacts.elastic.co/downloads/beats/metricbeat/metricbeat-7.0.1-x86_64.rpm```
    ```sudo rpm -vi metricbeat-7.0.1-x86_64.rpm```
    
9) Enable metricbeat to monitor httpd service.

    ```sudo metricbeat modules enable apache```

10) Disable metricbeat from monitoring the system

    ```sudo metricbeat modules disable system```

11) Start httpd service on the virtual machine instance.

    ```sudo systemctl start httpd.service```
    ```systemctl status httpd.service```    (to check status of httpd service)
    
12) Configure the output of metricbeat.
    
    - Go to /etc/metricbeat/metricbeat.yml
    
    - In Elastic Search Output, comment out the existing output and add the following output.
    
    - Store the output in a file by adding the following code:
    
    ```output.file:```
    ```path: "/tmp/metricbeat"```
    ```filename: metricbeat```

13) Restart httpd and metricbeat.

    ```sudo systemctl start httpd.service```
    ```sudo systemctl start httpd.service```
    ```sudo systemctl stop metricbeat.service```
    ```sudo systemctl stop metricbeat.service```


14) View the monitoring output.
    
    ```less /tmp/metricbeat/metricbeat.log```
  
