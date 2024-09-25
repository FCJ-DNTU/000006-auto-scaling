---
title : "Khởi tạo Target Group"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4.  </b> "
---

#### Khởi tạo Target Group

1. Truy cập giao diện **EC2**:
   - Chọn **Target Groups**
   - Chọn **Create target group**

![Deploy app](/images/14/0001.png?featherlight=false&width=90pc)

2. Thực hiện cấu hình:
   - Chọn **Instances**

![Deploy app](/images/14/0002.png?featherlight=false&width=90pc)

3. Trong trang **Specify group details**, thiết lập các thông số sau cho **target group**:
   - **Target group name**: Nhập tên của target group (VD: **FCJ-Management-TG**).
   - **Protocol**: HTTP.
   - **Port**: **5000** (Port sử dụng bởi FCJ Management).
   - Các mục còn lại để mặc định.

![Deploy app](/images/14/0003.png?featherlight=false&width=90pc)

4. Chọn **Next**

![Deploy app](/images/14/0004.png?featherlight=false&width=90pc)

5. Trong giao diện **Available instances**:
   - Chọn instance **FCJ-Management**
   - Chọn port **5000**
   - Chọn **Include as pending below** (nếu không chọn, khi truy cập bằng DNS Load Balancer có thể gặp lỗi **HTTP 503: Service unavailable**)
   - Kiểm tra lại
   - Chọn **Create target group**

![Deploy app](/images/14/0005.png?featherlight=false&width=90pc)

6. Trong giao diện **Register pending targets only**, chọn **Continue**

![Deploy app](/images/14/0006.png?featherlight=false&width=90pc)

7. Hoàn thành tạo **Target group**

![Deploy app](/images/14/0007.png?featherlight=false&width=90pc)
