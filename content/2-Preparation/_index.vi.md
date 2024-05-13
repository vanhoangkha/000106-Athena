---
title : "Chuẩn bị"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2. </b> "
---
# Chuẩn bị

## IAM role general
Chúng ta sẽ tạo một vài vai trò IAM chung:
1. Truy cập bảng điều khiển IAM:
    - Truy cập [Bảng điều khiển IAM](https://us-east-1.console.aws.amazon.com/iam/home?region=us-east-1#/home).
    - Trên thanh điều hướng bên trái, hãy chọn **Roles**
    - Lựa chọn **Create role**.
2. Tạo vai trò cho Glue.
   - Chọn **AWS Service**.
   - Nhập **Glue** trong "Use case".
   - Chọn **Next**.
   - Thêm quyền chúng ta cần
   - Nhập Tên vai trò
   - Chọn **Create role**.
   
   ![Image](/images/2/202.png?featherlight=false&width=90pc)
3. Tương tự với CloudFormation

    ![Image](/images/2/201.png?featherlight=false&width=90pc)

## Athena Spark
### CloudFormation Template
Trước khi bắt đầu hội thảo này, bạn cần tạo các tài nguyên AWS cần thiết. Để thực hiện việc này, chúng tôi cung cấp mẫu AWS CloudFormation để tạo ngăn xếp chứa tài nguyên. Khi bạn tạo ngăn xếp, AWS sẽ tạo một số tài nguyên trong tài khoản của bạn.


   - Bạn tải xuống [CloudFormation Template](/files/template.json)
   - Truy cập [ CloudFormation create console](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create?stackName=Athena-Spark-Workshop)
   - Chọn **Upload a template file**
   - Tải lên tệp mẫu( Bạn có thể xem chế độ Canvas trong **View in Application Composer**)

   ![Image](/images/2/2031.png?featherlight=false&width=90pc)

   - Chọn **Next**
   - Chọn vai trò CloudFormation của bạn trong Quyền

   ![Image](/images/2/203.png?featherlight=false&width=90pc)
   - Chọn tùy chọn xử lý lỗi của bạn
   - Chọn **Next**

   ![Image](/images/2/204.png?featherlight=false&width=90pc)
   - Nhập tên Stack của bạn 
   - Chọn **Next**

   - Chọn **Submit**

   ![Image](/images/2/205.png?featherlight=false&width=90pc)

   ![Image](/images/2/2051.png?featherlight=false&width=90pc)

### Tải lên tập dữ liệu và tạo bảng
1. Tải lên tập dữ liệu:
   - Bạn tải xuống tập dữ liệu [Financial Sample](/files/Financial.csv)
   - Tải lên vùng lưu trữ do CloudFormation tạo bằng đường dẫn: financial/Finacial.csv

   ![Image](/images/2/206.png?featherlight=false&width=90pc)

   ![Image](/images/2/207.png?featherlight=false&width=90pc)
2. Tạo cơ sở dữ liệu, bảng trong Glue Catalog
   - Truy cập [ Bảng điều khiển Cơ sở dữ liệu Glue](https://us-east-1.console.aws.amazon.com/glue/home?region=us-east-1#/v2/data-catalog/databases)
   - Chọn **Add database**
   - Nhập thông tin cơ sở dữ liệu

   ![Image](/images/2/208.png?featherlight=false&width=90pc)

   - Truy cập bảng điều khiển Glue Crawler
   - Chọn **Add Crawler**
   - Nhập thông tin crawler 

   ![Image](/images/2/209.png?featherlight=false&width=90pc)

   - Chọn crawler của bạn
   - Chọn **run**
   ![Image](/images/2/210.png?featherlight=false&width=90pc)

3. Kiểm tra dữ liệu trong Athena
   - Truy cập [ Bảng điều khiển Athena](https://us-east-1.console.aws.amazon.com/athena/home?region=us-east-1#/query-editor)
   - Kiểm tra truy vấn trong bảng &; tập dữ liệu của bạn

     ![Image](/images/2/211.png?featherlight=false&width=90pc)

## Athena Federation
### RDS 
   - Truy cập [ Cơ sở dữ liệu RDS](https://us-east-1.console.aws.amazon.com/rds/home?region=us-east-1#databases:)
   - Chọn **Create Database**
   - Trong phần này bạn có thể sử dụng VPC mặc định
   
     ![Image](/images/2/212.png?featherlight=false&width=90pc)
 
     ![Image](/images/2/213.png?featherlight=false&width=90pc)

     ![Image](/images/2/214.png?featherlight=false&width=90pc)
   - Khi bạn sử dụng Secret Manager

     ![Image](/images/2/215.png?featherlight=false&width=90pc)
