---
title: "Create Launch Template"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: "<strong>3. </strong>"
---

### Tạo Amazon Machine Images (AMIs) từ EC2

Ở bước này chúng ta sẽ khởi tạo Amazon Machine Images (AMI) cho EC2 vừa tạo ở các bước trước đó. AMIs chứa tất cả các thông tin cần thiết để khởi tạo một instance, bao gồm hệ điều hành, ứng dụng, và các cài đặt cấu hình.

1. Truy cập vào **EC2**

- Chọn **Instances**
- Chọn **FCJ-Management** instance
- Chọn **Actions**
- Chọn **Image and templates**
- Chọn **Create image**

![Create AMI](/images/3-create-launch-template/3.1.png)

2. Cấu hình cho AMI

- Đặt tên cho AMI, **Image name** **`FCJ-Management-AMI`**
- Nhập mô tả cho IMA, **Image description - optional** **`AMI for FCJ-Management`**
- Chọn **Create Image** để tiến hành tạo AMI

![Configure AMI](/images/3-create-launch-template/3.2.png)

3. Kiểm tra kết quả tạo AMI

- Chọn **AMIs** chúng ta sẽ thấy AMI vừa tạo được
- Chọn **FCJ-Management-AMI**
- Quá trình khởi tạo AMI sẽ mất khoảng 3 phút, sau quá trình khởi tạo chúng ta sẽ thấy **Status** của AMI chuyển từ trạng **Available**

![Check AMI](/images/3-create-launch-template/3.3.png)

Chúng ta vừa hoàn thành tạo một Image để lưu cấu hình của EC2

### Khởi tạo Launch Templates

Ở tiếp bước này chúng ta sẽ tạo **Launch Templates**.
Mục đích của việc khởi tạo **Launch Templates** là để tạo khuôn mẫu cho các EC2 Instances với **AMIs** đã được tạo trước đó.

1. Truy cập vào **Launch Templates**

- Chọn **Create launch template**

![Create launch template](/images/3-create-launch-template/3.4.png)

2. Cấu hình cho Launch Template

- Đặt tên cho template, **Launch template name - required** **`FCJ-Management-template`**

![Configure template](/images/3-create-launch-template/3.5.png)

- Nhập mô tả cho template, **Template version description** **`Template for FCJ Management`**

![Create launch template name](/images/3-create-launch-template/3.6.png)

- Chọn **My AMIs**
- Chọn **Owned by me**
- Chọn loại **Amazon Machine Image (AMI)**, chọn AMI đã tạo **FCJ-Management-AMI**

![Choose AMI](/images/3-create-launch-template/3.7.png)

- Chọn loại Instance **t2.micro**
- Chọn **Key pair name** có tên là **fcj-key**

![Configure Instance Type](/images/3-create-launch-template/3.8.png)

Ở phần **Network settings**

- Chọn subnet public **AutoScaling-Lab-public-ap-southeast-1a**
- Chọn **Select existing security group**
- Chọn security group **FCJ-Management-SG**
- Cuối cùng, chọn **Create launch template**

![Configure Networking](/images/3-create-launch-template/3.9.png)

3. Kiểm tra Launch Template vừa tạo

- Chọn vào Launch Template vừa tạo, **FCJ-Management-template**

![Check Template](/images/3-create-launch-template/3.10.png)

- Ở đây chúng ta có thể xem lại cấu hình Launch Template chúng ta đã tạo

![Check Configure Template](/images/3-create-launch-template/3.11.png)
