# Configure proxy server for New Relic infrastructure agent
## Step 1 - Install a Squid server (15 minutes)
### Install Squid
At a terminal prompt, enter the following command to install the Squid server:
```
sudo apt install squid
```
### Configure Squid
Squid is configured by editing directives in the /etc/squid/squid.conf configuration file.
#### Change TCP port
The default TCP port of Squid is 3128, to set your Squid server to listen on TCP port 8888 instead of the default port, change the http_port directive as such:
```
http_port 8888
```
#### Access control
You can configure use of Squid-proxied Internet services to be available only to users with certain Internet Protocol (IP) addresses. To simply allow all IP address, add the following to the top of configuration file:
```
http_access allow all
```
Or only allow access by users of the 192.168.100.0/24 subnetwork only instead of all IP addresses:
```
acl inner_network src 192.168.100.0/24
http_access allow inner_network
```
After configuring access coutrol, you can easily see all requests in /var/log/squid/access.log file.
#### Restart the Squid server
After making any changes to the /etc/squid/squid.conf file, you will need to save the file and restart the squid server application. You can restart the server using the following command:
```
sudo systemctl restart squid.service
```
## Step 2 - Prepare a machine ready to be managed (15 minutes)
Recommend to use an online server for installing the infrastructure agent.
## Step 3 - Install the infrastructure agent (15 minutes)
The quickest way to get started with New Relic infrastructure monitoring agent is through guided install.
### Log in New Relic platform
Sign up for a [free New Relic account](https://newrelic.com/signup) and log in [New Relic platfotm](https://one.newrelic.com).
### Determine the OS type (take Windows for exambple)
![2024-05-02_113837](https://github.com/mars0426/NewRelic/assets/42570850/3d6c1ef1-6f1d-429a-b1e0-aeee877daaa5)
### Enter user key
![2024-05-02_114509](https://github.com/mars0426/NewRelic/assets/42570850/8c720e1d-5e71-4cbc-bc5a-522e62717f25)
### Enter proxy server address and copy provided code
![2024-05-02_114701](https://github.com/mars0426/NewRelic/assets/42570850/390f06e6-4542-4279-9765-7cee56c6f428)
### Install the infrastructure agent
Navigate to Windows PowerShell on your computer, right-click the PowerShell app, and click “Run as Administrator.” Then, copy the provided code into the command prompt and press Enter.
