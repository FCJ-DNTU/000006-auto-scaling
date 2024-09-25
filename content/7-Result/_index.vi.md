---
title : "Kiểm tra kết quả"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 7.   </b> "
---

#### Kiểm tra kết quả

Trong bài thực hành này, chúng ta sẽ kiểm tra truy cập tới **ShareNote** và tiến hành tăng số lượng yêu cầu truy cập đến ứng dụng thông qua việc mở đồng loạt nhiều kết nối sử dụng công cụ *Webserver Stress Tool 8*. Bạn hãy nhấn vào [Webserver Stress Tool 8](https://www.paessler.com/tools/webstress) để tải về.

1. Thực hiện tải **Webserver Stress Tool 8**

![Auto Scaling Group](/images/17/0001.png?featherlight=false&width=90pc)

2. Kiểm tra khả năng tự mở rộng của ứng dụng **FCJ Management** được triển khai

   - Giải nén file zip và cài đặt *Webserver Stress Tool 8* với tùy chọn mặc định.
   - Khởi động *Webserver Stress Tool 8* để tiến hành tạo số lượng truy cập lớn đến *Endpoint* của *Load Balancer*.
   - Nhấn vào tab **Test Type** và nhập thông số như hình dưới đây:
     - Run Unit: 100000
     - Number of Users: 101
     - Click Delay: 1

![Auto Scaling Group](/images/17/0001.png?featherlight=false&width=90pc)

3. Nhấn vào tab **URLs**, copy `DNSName` của ứng dụng **FCJ Management** vào ô URL (DNSName khi bạn tạo *Load Balancer* ở bước 5.Khởi tạo Load Balancer), và nhấn **Start Test**

![Auto Scaling Group](/images/17/0002.png?featherlight=false&width=90pc)

![Auto Scaling Group](/images/17/0003.png?featherlight=false&width=90pc)

4. Sau một khoảng thời gian, kiểm tra phản hồi của *Auto Scaling Group*. Ta thấy số lượng instance được tăng lên số lượng tối đa mà chúng ta thiết lập là 3.

![Auto Scaling Group](/images/17/0004.png?featherlight=false&width=90pc)

![Auto Scaling Group](/images/17/0006.png?featherlight=false&width=90pc)

![Auto Scaling Group](/images/17/0008.png?featherlight=false&width=90pc)

![Auto Scaling Group](/images/17/0009.png?featherlight=false&width=90pc)

5. Kiểm tra truy cập vào ứng dụng từ trình duyệt không bị gián đoạn.

![Load Balancer](/images/15/0009.png?featherlight=false&width=90pc)

6. Xem kết quả logfile

![Auto Scaling Group](/images/17/0005.png?featherlight=false&width=90pc)

![Auto Scaling Group](/images/17/0007.png?featherlight=false&width=90pc)

7. Xem giao diện của **EC2** khi chạy ứng dụng.

![Auto Scaling Group](/images/17/00010.png?featherlight=false&width=90pc)

Chúc mừng bạn vừa hoàn thành bài thực hành *Triển khai ứng dụng FCJ Management với Auto Scaling Group và Elastic Load Balancer*.

Bạn sẽ nhận được mail thông báo.

![Auto Scaling Group](/images/17/00013.png?featherlight=false&width=90pc)
