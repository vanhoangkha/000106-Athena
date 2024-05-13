---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

## Giới thiệu 
Trong workshop này, chúng ta sẽ sử dụng:
- **IAM:** IAM cung cấp khả năng kiểm soát truy cập chi tiết trên toàn bộ AWS. Với IAM, bạn có thể kiểm soát quyền truy cập vào các dịch vụ và tài nguyên theo các điều kiện cụ thể. Sử dụng chính sách IAM để quản lý quyền cho lực lượng lao động và hệ thống của bạn. IAM được cung cấp miễn phí.


- **S3:** Amazon S3 là bộ lưu trữ đối tượng trên đám mây với khả năng mở rộng, tính khả dụng của dữ liệu, tính bảo mật và hiệu suất dẫn đầu ngành. S3 lý tưởng cho các hồ dữ liệu, ứng dụng di động, sao lưu và khôi phục, lưu trữ, thiết bị IoT, ML, AI và phân tích.


- **Athena:** Amazon Athena là dịch vụ truy vấn tương tác giúp dễ dàng phân tích dữ liệu trong Amazon S3 bằng SQL tiêu chuẩn. Athena không có máy chủ nên không cần quản lý cơ sở hạ tầng và bạn chỉ phải trả tiền cho những truy vấn mình chạy. Athena rất dễ sử dụng. Chỉ cần trỏ tới dữ liệu của bạn trong Amazon S3, xác định lược đồ và bắt đầu truy vấn bằng SQL tiêu chuẩn. Hầu hết các kết quả được gửi trong vòng vài giây. Với Athena, bạn không cần thực hiện các công việc ETL phức tạp để chuẩn bị dữ liệu cho việc phân tích. Điều này giúp bất kỳ ai có kỹ năng SQL có thể dễ dàng phân tích nhanh các bộ dữ liệu quy mô lớn. Athena được tích hợp ngay với Danh mục dữ liệu AWS Glue, cho phép bạn tạo kho lưu trữ siêu dữ liệu thống nhất trên nhiều dịch vụ khác nhau, thu thập thông tin nguồn dữ liệu để khám phá lược đồ và điền vào Danh mục của bạn các định nghĩa phân vùng và bảng mới và được sửa đổi, đồng thời duy trì lược đồ phiên bản.


- **CloudFormation:** AWS CloudFormation là dịch vụ giúp bạn lập mô hình và thiết lập tài nguyên AWS để bạn có thể dành ít thời gian hơn cho việc quản lý các tài nguyên đó và có nhiều thời gian hơn để tập trung vào các ứng dụng chạy trong AWS. Bạn tạo một mẫu mô tả tất cả tài nguyên AWS mà bạn muốn (như phiên bản Amazon EC2 hoặc phiên bản Amazon RDS DB) và CloudFormation sẽ đảm nhiệm việc cung cấp và đặt cấu hình các tài nguyên đó cho bạn. Bạn không cần phải tạo và đặt cấu hình riêng các tài nguyên AWS cũng như tìm hiểu xem cái gì phụ thuộc vào cái gì; CloudFormation xử lý việc đó. Các tình huống sau đây minh họa cách CloudFormation có thể trợ giúp.


- **RDS:** Amazon RDS là dịch vụ cơ sở dữ liệu quan hệ dễ quản lý được tối ưu hóa cho tổng chi phí sở hữu. Thật đơn giản để thiết lập, vận hành và mở rộng quy mô theo nhu cầu. Amazon RDS tự động hóa các tác vụ quản lý cơ sở dữ liệu không phân biệt, chẳng hạn như cung cấp, đặt cấu hình, sao lưu và vá lỗi. Amazon RDS cho phép khách hàng tạo cơ sở dữ liệu mới trong vài phút và mang lại sự linh hoạt trong việc tùy chỉnh cơ sở dữ liệu nhằm đáp ứng nhu cầu của họ trên 8 công cụ và 2 tùy chọn triển khai. Khách hàng có thể tối ưu hóa hiệu suất bằng các tính năng, như Multi-AZ với hai chế độ chờ có thể đọc được, Ghi và đọc được tối ưu hóa cũng như các phiên bản dựa trên AWS Graviton3, đồng thời chọn từ nhiều tùy chọn giá để quản lý chi phí một cách hiệu quả.