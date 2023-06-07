## Scenario:
During the daily standup, it was pointed out that the timezone across Nautilus Application Servers in Stratos Datacenter doesn't match with that of the local datacenter's timezone, which is America/Nassau.

## Steps:
Note: You need to do below to all application server
* SSH to your assigned host/server
```
ssh <user>@<servername>
```
* Check the current timezone
```
timedatectl
```
* List the available timezones
```
timedatectl list-timezones
```
* Set the timezone of the server
```
sudo timedatectl set-timezone America/Nassau
```
* Verify the timezone has been set to the correct one
```
timedatectl
```