## Scenario:
The System admin team of `xFusionCorp Industries` has installed a backup agent tool on all app servers. As per the tool's requirements they need to create a user with a non-interactive shell.
Therefore, create a user named `mark` with a non-interactive shell on the `App Server 2`

## Steps:
* SSH to your assigned host/server
```
ssh <user>@<servername>
```
* Check if the user exists already
```
id <username>
```
* Add the user with a non-interactive shell
```
adduser <username>  -s /sbin/nologin
```
* To check/confirm for non-interactive shell
```
cat /etc/passwd | grep <username>
```