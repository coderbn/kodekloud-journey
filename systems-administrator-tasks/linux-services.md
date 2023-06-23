## Scenario:
As per details shared by the development team, the new application release has some dependencies on the back end.
There are some packages/services that need to be installed on `all app servers` under Stratos Datacenter. As per requirements please perform the following steps.
- Install Name Service Cache Daemon `nscd` package on all the application servers.
- Once installed, make sure it is `enabled to start during boot`.

## Steps:
Note: You need to do below to all application server
* SSH to your assigned host/server
```
ssh <user>@<servername>
```
* Switch user to root to have admin access
```
sudo su - root
```
* Install the `nscd` service
```
yum install <service name> -y
```
* Start the service
```
systemctl start <service name>
```
* Configure the service to start at startup
```
systemctl enable <service name>
```
* Check the status of the service
```
systemctl status <service name>
```