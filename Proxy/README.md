# Configure proxy server for New Relic infrastructure agent
## Step 1 - Install a Squid server
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
## Step 2 - Install the infrastructure agent
The quickest way to get started with New Relic infrastructure monitoring agent is through guided install.
### Log in New Relic platform
Sign up for a [free New Relic account](https://newrelic.com/signup) and log in [New Relic platfotm](https://one.newrelic.com).
### Determine the OS type
