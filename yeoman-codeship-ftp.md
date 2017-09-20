# Config for Yeoman-Angular projects deploy on Codeship via FTP

1. Create your project in codeship
2. Connect your github repository to the project
3. In your codeship project "Test" section, save this script: 
	`npm install`
4. In the "Environment" section configure your FTP env variables : $FTP_USER, $FTP_PASSWORD, $FTP_HOST, $FTP_SITE_DIR (the path where your site will be saved on the remote server)
5. At the "Deployment" section place the following script
	```
	grunt build
	chmod -R 774 ${HOME}/clone/dist
	lftp -c "open -u $FTP_USER,$FTP_PASSWORD $FTP_HOST; set ssl:verify-certificate no; mirror -R ${HOME}/clone/dist $FTP_SITE_DIR"

6. Save and push to your git repo to deploy