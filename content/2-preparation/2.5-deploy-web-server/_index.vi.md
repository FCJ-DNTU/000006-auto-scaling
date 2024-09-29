---
title: "Triển khai máy chủ web"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: "<strong>2.5. </strong>"
---

1. Cài đặt node version manager (nvm) bằng cách nhập nội dung sau:
   
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
4. Đến thư mục của bài lab 000004-EC2

```
cd 000004-EC2
```

5. NPM là viết tắt của Node package manager là một công cụ tạo và quản lý các thư viện lập trình Javascript cho Node.js. Sử dụng npm init khởi tạo project sẽ tạo ra file package.json mẫu. 

```
npm init

```

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.3.png?featherlight=false&width=90pc)

6. Cài đặt **pm2** trong Global, PM2 được sử dụng để quản lý và giám sát các ứng dụng Node.js đang chạy. Nó cho phép các ứng dụng chạy dưới nền.
```
npm install -g pm2
```

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.4.png?featherlight=false&width=90pc)

7. Tiếp theo, chúng ta định nghĩa lại câu script để chạy ứng dụng, chúng ta sẽ dùng **vim** để mở file pakage.json, trong phần scripts ở key **start**, gán cho nó value sau, điều này sẽ giúp ứng dụng của chúng ta chạy nền: 
```
pm2 start app.js
```


![Image](/images/2-preparation/2.5-deploy-web-server/2.5.5.png?featherlight=false&width=90pc)

8. Tiếp tục dùng vim để vào file .env, sau đó nhập vào nội dung sau để thiết lập kết nối tới database.


```
DB_HOST = 'fcj-management-db-instance.cdysiiecu90g.ap-southeast-1.rds.amzonaws.com'
DB_NAME = 'awsfcjuser'
DB_USER = 'admin'
DB_PASS = '123Vodanhphai'
```


![Image](/images/2-preparation/2.5-deploy-web-server/2.5.6.png?featherlight=false&width=90pc)


9. Tiến hành khởi chạy ứng dụng:
```
npm start
```
10.  Lệnh **``pm2 status``** trong PM2 được sử dụng để hiển thị trạng thái hiện tại của tất cả các ứng dụng đang được quản lý bởi PM2. Khi bạn chạy lệnh này, chúng ta sẽ nhận được thông tin tổng quan về từng ứng dụng.

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.7.png?featherlight=false&width=90pc)

11. Tiếp theo, chúng ta cần lấy được public DNS của instance để có thể truy cập được ứng dụng từ trình duyệt.

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.8.png?featherlight=false&width=90pc)

12. Ứng dụng của chúng ta đã chạy ổn định.

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.9.png?featherlight=false&width=90pc)

13.  Tiếp theo chúng ta dùng câu lệnh **``pm2 startup``** để tiến hành cấu hình PM2 tự động khởi động lại các ứng dụng khi máy chủ khởi động lại.
14.  Nó sẽ yêu cầu thiết lập Startup Script, hãy copy/paste command đó và chạy.

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.10.png?featherlight=false&width=90pc)

15.  Để đảm bảo các ứng dụng đang chạy được lưu lại và khởi động lại khi server khởi động lại, chúng ta cần chạy lệnh **``pm2 save``**. Lệnh này sẽ lưu trạng thái hiện tại của các tiến trình vào danh sách khởi động.

![Image](/images/2-preparation/2.5-deploy-web-server/2.5.11.png?featherlight=false&width=90pc)