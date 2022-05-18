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


Starting, stopping, and restarting Jenkins on Ubuntu
Jenkins by default starts running when installed. Here are the commands to start, stop, restart, and check the status of the Jenkins service:

To start Jenkins, use the following command:
        sudo systemctl start jenkins 
Similarly, to stop Jenkins, use the following command:
        sudo systemctl stop jenkins 
To restart Jenkins, use the following command:
        sudo systemctl restart jenkins 
To check the status of the Jenkins service, use the following systemctl command:
        sudo systemctl status jenkins 



//////////////// HTTPS //////////////////

https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04

sudo certbot --nginx -d saavn.click -d www.saavn.click

sudo ln -f /etc/nginx/sites-available/saavn.click /etc/nginx/sites-enabled/saavn.click

sudo certbot --nginx -d saavn.click -d www.saavn.click


pm2 serve . 3000 --spa --name "reactjs"

