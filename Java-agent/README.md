# Config Java agent to use proxy server
## Step 1 - Install the Java agent (30 minutes)
The quickest way to get started with New Relic application monitoring agent is through guided install.
### Log in New Relic platform
Sign up for a [free New Relic account](https://newrelic.com/signup) and log in [New Relic platfotm](https://one.newrelic.com).
### Install the Java agent
Install the Java agent using [guided install](https://one.newrelic.com/marketplace/install-data-source?state=f91bc85d-0574-6e23-b90a-4d89c7c12866)
## Step 2 - Configure the Java agent (10 minutes)
The New Relic Java agent reads its configuration from the newrelic.yml file. By default the agent looks for this file in the directory that contains newrelic.jar.
### Set proxy_host in the common section
```
proxy_host: 192.168.100.105
```
### Set proxy_port in the common section
```
proxy_host: 3128
```
### Set proxy_user in the common section (optional)
```
proxy_user: proxy_user
```
### Set proxy_password in the common section (optional)
```
proxy_password: proxy_password
```
## Step 3 - Restart the JVM to apply changes (5 minutes)
