# Config for Codeship rsync deploy

1. Create your project in codeship
2. Connect your github repository to the project
3. At the "Deployment" section place the following script replacing the `ssh_user`, `your.server.com` and `/path/on/server values`
	```
	rsync -avz ~/clone/ ssh_user@your.server.com:/path/on/server/
	```
4. In the "General" section of your codeship project, at the bottom of the page copy the project ssh key.
5. In your remote server, add your codeship ssh project key to this file `~/.ssh/authorized_keys
` . You have to paste the ssh key in a new line insde the file.
6. Save the authorized_keys file.
7. Save and push to your git repo to deploy


Source: (https://documentation.codeship.com/basic/continuous-deployment/deployment-with-ftp-sftp-scp/)[https://documentation.codeship.com/basic/continuous-deployment/deployment-with-ftp-sftp-scp/]