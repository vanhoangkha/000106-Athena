---
title : "Dọn dẹp tài nguyên"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---
## Dọn dẹp

Chúng tôi sẽ tiến hành xóa các tài nguyên theo thứ tự sau:

Khi bạn đã hoàn thành hội thảo này, hãy nhớ dọn dẹp tất cả các tài nguyên AWS mà bạn đã tạo bằng AWS CloudFormation.

Làm theo các bước dưới đây để dọn dẹp:
### Athena Spark

- Bạn sẽ cần phải tự làm trống S3Bucket athena-spark-workshop được tạo bởi CloudFormation vì CloudFormation chỉ có thể xóa vùng lưu trữ S3 khi nó trống.

- Sử dụng bảng điều khiển AWS CloudFormation hoặc AWS CLI để xóa ngăn xếp có tên Athena-Spark-Workshop.

   ![Image](/images/5/501.png?featherlight=false&width=90pc)
### Athena Federation

1. [ ] Xóa VPC endpoint

   ![Image](/images/5/503.png?featherlight=false&width=90pc)
2. [ ] Xóa cơ sở dữ liệu trong RDS

   ![Image](/images/5/504.png?featherlight=false&width=90pc)
3. [ ] Xóa hàm Lambda

   ![Image](/images/5/501.png?featherlight=false&width=90pc)
4. [ ] Xóa vai trò IAM của Lambda
5. [ ] Bạn sẽ cần phải tự làm trống S3Bucket được tạo cho Athena, sau đó xóa nó.

