## Scenario:
The system admin team of `xFusionCorp Industries` has noticed an issue with some servers in Stratos Datacenter where some of the servers are not in sync w.r.t time. Because of this, several application functionalities have been impacted. To fix this issue the team has started using common/standard NTP servers. They are finished with most of the servers except `App Server 3`. Therefore, perform the following tasks on this server:
- Install and configure NTP server on App Server 3.
- Add NTP server `3.pool.ntp.org` in NTP configuration on `App Server 3`.
- Please `do not try to start/restart/stop ntp service`, as we already have a restart for this service scheduled for tonight and we don't want these changes to be applied right now.

## Steps:
* SSH to your assigned host/server
```
ssh <user>@<servername>
```
* Switch user to root to have admin access
```
sudo su - root
```
* Check if ntp has been installed
```
rpm -qa | grep ntp
```
* Install the ntp and its corresponding component
```
yum install -y ntp
```
* Edit the ntp.conf, and put in the needed ntp server `3.pool.ntp.org`
```
vi /etc/ntp.conf
```
* Verify if you've updated the file successfully, it should have a value of `server 3.pool.ntp.org`
```
cat /etc/ntp.conf | grep 3.pool
```
* Check the ntp daemon if it's running or not
```
ntpstat
```
* Check the status of ntpd service
```
systemctl status ntpd
```
* Configure the service to start at startup
```
systemctl enable ntpd
```
* Do only below if it is required to be started
```
systemctl start ntpd
```