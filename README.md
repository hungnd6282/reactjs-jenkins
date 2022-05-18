# reactjs-jenkins
Example jenkins auto build with github


sudo ln -sf ../sites-available/react-tutorial ../sites-enabled/

sudo ln -s /etc/nginx/sites-available/jenkins-react-app /etc/nginx/sites-enabled/jenkins-react-app

npm install -g serve
npm install -g pm2

npm run build 

pm2 serve <path> <port>

example: pm2 serve build 3000 --spa --name "reactjs"


https://www.loginradius.com/blog/engineering/react-app-deployment/


Install jenkins

https://devopsarticle.com/how-to-install-jenkins-on-aws-ec2-ubuntu-20-04/


Jenkins using sudo
https://stackoverflow.com/questions/17940612/authentication-error-in-jenkins-on-using-sudo

service jenkins start/stop/restart


