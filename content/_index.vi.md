---
title: "Triển khai ứng dụng FCJ Management với Auto Scaling Group"
date: "`r Sys.Date()`"
weight: 1
chapter: false
---

# Triển khai ứng dụng FCJ Management với Auto Scaling Group

#### Tổng quan

Trong hướng dẫn này, chúng ta sẽ thực hiện triển khai ứng dụng bằng cách sử dụng Auto Scaling Group để đảm bảo khả năng mở rộng linh hoạt theo nhu cầu của người truy cập. Ngoài ra, chúng ta cũng sẽ triển khai Load Balancer để cân bằng tải và phân phối yêu cầu từ người dùng đến Application Tier của ứng dụng.

Hãy đảm bảo bạn đã xem qua tài liệu [Triển khai Ứng dụng FCJ Management trên Máy ảo Windows/AmazonLinux](https://000004.awsstudygroup.com/) để nắm vững cách triển khai ứng dụng trên máy ảo. Chúng ta sẽ cần sử dụng máy ảo **FCJ Management** đã triển khai để thực hiện việc triển khai đồng loạt và mở rộng trong Auto Scaling Group.

#### Auto Scaling Group

**Auto Scaling Group** (nhóm co giãn tự động) là một nhóm các EC2 Instance. Nhóm này có khả năng tự động điều chỉnh số lượng các EC2 Instance thành viên dựa trên các chính sách co giãn mà bạn đặt ra.

#### Launch Template

**Launch Template** (khuôn mẫu khởi tạo) là một tính năng cho phép bạn tạo ra các khuôn mẫu để khởi tạo EC2 Instance. Điều này giúp bạn tự động hóa và đơn giản hóa việc khởi tạo các EC2 Instance cho dịch vụ Auto Scaling (co giãn tự động).

#### Load Balancer

**Load Balancer** (máy cân bằng tải) là một công cụ cho phép phân phối lưu lượng dữ liệu tới các tài nguyên AWS (trong trường hợp này là các EC2 Instances) trong một Target Group cụ thể.

#### Target Group

**Target Group** (nhóm mục tiêu) là một nhóm các tài nguyên AWS sẽ nhận lưu lượng dữ liệu từ Load Balancer và tiếp tục truyền chuyển nó.

![Auto Scaling Group](/images/2-Prerequiste/0.png?featherlight=false&width=50pc)

#### Nội dung

1. [Giới thiệu](1-introduction/)
2. [Các bước chuẩn bị](2-preparation/)
3. [Khởi tạo Template](3-create-launch-template/)
4. [Thiết lập Load Balancer](4-setup-load-balancer/)
5. [Kiểm thử](5-test/)
6. [Khởi tạo Auto Scaling Group](6-create-auto-scaling-group/)
7. [Kiểm thử các giải pháp](7-test-solutions/)
8. [Dọn dẹp tài nguyên](8-cleanup/)
