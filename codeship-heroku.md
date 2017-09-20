# Config for Heroku projects on Codeship


1. Create your project in codeship
3. Connect your github repository to the project
4. Get your Heroku API key in https://dashboard.heroku.com/account
5. In the codeship deploy section choose "Heroku" and place your heroku app name and your heroku API key
6. Save changes in codeship
7. In the codeship project, go to "General" section, at the bottom and copy the SSH key
8. In your heroku account (https://dashboard.heroku.com/account) add your Codeship project to your "Registered SSH Keys"


7. Push to your configured repository.


*Source: https://documentation.codeship.com/basic/continuous-deployment/deployment-to-heroku/
NOTE: In the link above, Codeship doesn't mention the ssh key configuration (step 7)