---
title: "Deploy Web Server"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: "<strong>2.5. </strong>"
---

1. Install Node Version Manager (nvm) by entering the following command into the terminal:
   
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.0/install.sh | bash
```

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.1.png?featherlight=false&width=90pc)

2. Sử dụng nvm để cài đặt  Node.js bằng cách nhập nội dung sau vào dòng lệnh.

```
nvm install 20
```

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.2.png?featherlight=false&width=90pc)

3. Thực hiện clone repository code ứng dụng
   
```
git clone https://github.com/First-Cloud-Journey/000004-EC2.git
```
4. Navigate to the directory for lab 000004-EC2

```
cd 000004-EC2
```

5. NPM, short for Node Package Manager, is a vital tool for managing JavaScript libraries and dependencies in Node.js applications.When you run the command npm init, it initializes a new Node.js project and creates a package.json file. This file contains metadata about the project, such as its name, version, description, and a list of dependencies.
   

```
npm init

```

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.3.png?featherlight=false&width=90pc)

6. Install pm2 globally; PM2 is used to manage and monitor running Node.js applications. It allows applications to run in the background.
```
npm install -g pm2
```

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.4.png?featherlight=false&width=90pc)

7. Next, we redefine the script to run the application. We will use vim to open the package.json file and in the scripts section under the key start, assign it the following value. This will allow our application to run in the background: 
```
pm2 start app.js
```


![Image](/images/2-preparation/2.5-deploy-web-server/2.5.5.png?featherlight=false&width=90pc)

8. Continue using vim to access the .env file, then enter the following content to set up the connection to the database.


```
DB_HOST = 'fcj-management-db-instance.cdysiiecu90g.ap-southeast-1.rds.amzonaws.com'
DB_NAME = 'awsfcjuser'
DB_USER = 'admin'
DB_PASS = '123Vodanhphai'
```


![Image](/images/2-preparation/2.5-deploy-web-server/2.5.6.png?featherlight=false&width=90pc)


9. Proceed to start the application.
```
npm start
```
10.  The command **``pm2 status``** in PM2 is used to display the current status of all applications being managed by PM2. When you run this command, you'll receive an overview of each application, including details like their state (running, stopped, etc.), memory usage, CPU usage, and the number of restarts. This helps in monitoring the performance and health of your Node.js applications effectively.

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.7.png?featherlight=false&width=90pc)

11. Next, we need to obtain the public DNS of the instance so that we can access the application from the browser.

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.8.png?featherlight=false&width=90pc)

12. Our application is running stably

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.9.png?featherlight=false&width=90pc)

13.  Next, we use the command **``pm2 startup``** to configure PM2 to automatically restart applications when the server reboots.
14.  It will prompt you to set up a Startup Script. Please copy and paste that command and execute it.

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.10.png?featherlight=false&width=90pc)

15.  To ensure that the running applications are saved and restarted when the server reboots, we need to run the command **``pm2 save``**. This command will save the current state of the processes to the startup list.

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.11.png?featherlight=false&width=90pc)