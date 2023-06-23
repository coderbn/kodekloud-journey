## Scenario:
New tools have been installed on the app server in `Stratos Datacenter`. Some of these tools can only be managed from the graphical user interface. Therefore, there are requirements for these app servers.
On `all App servers` in Stratos Datacenter change the `default runlevel` so that they can boot in GUI (graphical user interface) by default.

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
* Check the default run level
```
systemctl get-default
```
* Change the run level to `graphical.target`
```
systemctl set-default graphical.target
```
* Validate the status
```
systemctl status graphical.target
```
* Start the graphical service
```
systemctl start graphical.target
```
* Validate the status again
```
systemctl status graphical.target
```
* Check the default run level
```
systemctl get-default
```