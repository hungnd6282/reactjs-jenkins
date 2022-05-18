# reactjs-jenkins
Example jenkins auto build with github

//////////////// INSTALL JENKINS AND NODEJS //////////////////

https://medium.com/swlh/setup-a-ci-cd-pipeline-to-automate-react-app-deployment-on-aws-ec2-82bd0c194f77

//////////////// CONFIG NGINX //////////////////
sudo vi /etc/nginx/sites-available/jenkins-react-app

server {                                                                 
listen 80;                                                               
  server_name 18.142.183.140;//IPv4 public host

    access_log /var/log/nginx/jenkins-react-app.com.access.log;
    error_log /var/log/nginx/jenkins-react-app.com.error.log;
    location / {
        proxy_pass http://localhost:3000;                                 
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}

sudo ln -s /etc/nginx/sites-available/jenkins-react-app /etc/nginx/sites-enabled/jenkins-react-app


//////////////// install pm2 //////////////////
npm install -g serve
npm install -g pm2

npm run build

pm2 serve <path> <port>
example: pm2 serve build 3000 --spa --name "reactjs"


https://www.loginradius.com/blog/engineering/react-app-deployment/


Install Jenkins
https://devopsarticle.com/how-to-install-jenkins-on-aws-ec2-ubuntu-20-04/


Jenkins using sudo
https://stackoverflow.com/questions/17940612/authentication-error-in-jenkins-on-using-sudo

sudo service jenkins start/stop/restart


