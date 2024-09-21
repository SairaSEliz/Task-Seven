# OpenVAS Installation and Scanning on Metasploitable VM (IP: 10.0.2.4)

This guide outlines the steps to install OpenVAS using Docker, perform an OpenVAS scan on the Metasploitable VM (IP: 10.0.2.4), generate a PDF report, create an HTML Nikto report, and grab a banner using netcat.

## Step 1: Install Docker and Run OpenVAS

### Install Docker
Run the following command to install Docker:
```bash
sudo apt install docker.io
```

### Pull and Run the OpenVAS Container
Use Docker to pull and run the OpenVAS container:

```bash
sudo docker run -d -p 443:443 --name openvas mikesplain/openvas
```
This will download the OpenVAS Docker image and run it on port 443.

### Start the OpenVAS Container
If you ever need to restart the container, use this command:

```bash
sudo docker start openvas
```
Once the container is running, OpenVAS will be accessible via your browser at:

```arduino
https://127.0.0.1
```
Use the default credentials to log in:

Username: admin
Password: admin

## Step 2: Perform an OpenVAS Scan on Metasploitable VM (IP: 10.0.2.4)

Access OpenVAS
Open your browser and go to https://127.0.0.1.
Login with the default credentials.
Configure and Run a Scan
In the OpenVAS interface, create a new task.
Set the target IP to 10.0.2.4 (Metasploitable VM).
Start the scan.
Download the Report as PDF
After the scan completes, navigate to the Reports section.
Export the scan report as a PDF.
Save the PDF for documentation purposes.

## Step 3: Generate an HTML Nikto Report for Metasploitable VM
Nikto is a web server scanner that looks for vulnerabilities. Here's how to run it on the Metasploitable VM.

Install Nikto
If Nikto is not installed, use the following command:

```bash
sudo apt install nikto
```
Run Nikto Scan
Run a Nikto scan on the Metasploitable VM’s IP (10.0.2.4):

```bash
nikto -h http://10.0.2.4 -output metasploitable_nikto_report.html
```
This command generates an HTML report (metasploitable_nikto_report.html) with the scan results.

## Step 4: Grab the Banner Using Netcat
Netcat Command
Use netcat to grab the banner for any port (for example, port 21 on Metasploitable VM):

```bash
nc 10.0.2.4 21
```
The above command will display the banner for the FTP service running on port 21. Once the banner is displayed, take a screenshot and save it.
