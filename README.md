# Spark-and-Mapreduce
Trình bày tổng quan về Apache Spark và Mapreduce
# I. Tổng quan về Apache Spark
## 1. Giới thiệu
  Apache Spark là một open source cluster computing framework được phát triển vào năm 2009 bởi AMPLab tại đại học California. Sau này, Spark đã được truyền lại cho Apache Software Foundation vào năm 2013 và được phát triển cho đến nay.

  Apache Spark  cho phép xây dựng các predition model ( mô hình dự đoán) nhanh chóng với việc tính toán được thực hiện trên một nhóm các máy tính, nó có thể tính toán cùng lúc trên toàn bộ tập dữ liệu mà không cần phải trích xuất mẫu tính toán thử nghiệm. Tốc độ xử lý của Spark dựa trên việc tính toán được thực hiện cùng lúc trên nhiều máy khác nhau. Đồng thời việc tính toán được thực hiện ở bộ nhớ trong (in-memories) hay thực hiện hoàn toàn trên RAM.
 
 ## 2. Các thành phần của Apache Spark
  Matei Zaharia là cha đẻ của Spark, ông này sử dụng Hadoop từ những ngày đầu phát triển spark. Đến năm 2009 ông viết Apache Spark để giải quyết những bài toán học máy ở đại học UC Berkely vì Hadoop MapReduce hoạt động không hiệu quả cho những bài toán này. Sau đó ông nhận ra rằng Spark không chỉ hữu ích cho học máy mà còn cho cả việc xử lý luồng dữ liệu hoàn chỉnh.
  
  Thành phần cơ bản của Spark là Spark Core: cung cấp những chức năng cơ bản nhất của Spark như lập lịch cho các tác vụ, quản lý bộ nhớ, fault recovery, tương tác với các hệ thống lưu trữ…Đặc biệt, Spark Core cung cấp API để định nghĩa RDD (Resilient Distributed DataSet) là tập hợp của các item được phân tán trên các node của cluster và có thể được xử lý song song.
  
  Spark có thể chạy trên nhiều loại Cluster Managers như Hadoop YARN, Apache Mesos hoặc trên chính cluster manager được cung cấp bởi Spark được gọi là Standalone Scheduler.
  
  Spark SQL cho phép truy vấn dữ liệu cấu trúc qua các câu lệnh SQL. Spark SQL có thể thao tác với nhiều nguồn dữ liệu như Hive tables, Parquet, và JSON.
  
  Spark Streaming cung cấp API để dễ dàng xử lý dữ liệu stream
MLlib Cung cấp rất nhiều thuật toán của học máy như: classification, regression, clustering, collaborative filtering… Còn GraphX là thư viện để xử lý đồ thị.
## 3. Những tính năng nổi bật
- “Spark as a Service”: Giao diện REST để quản lí (submit, start, stop, xem trạng thái) spark job, spark context
- Tăng tốc, giảm độ trễ thực thi job xuống mức chỉ tính bằng giây bằng cách tạo sẵn spark context cho các job dùng chung.
- Stop job đang chạy bằng cách stop spark context
- Bỏ bước upload gói jar lúc start job làm cho job được start nhanh hơn.
- Cung cấp hai cơ chế chạy job đồng bộ và bất đồng bộ
- Cho phép cache RDD theo tên , tăng tính chia sẻ và sử dụng lại RDD giữa các job
- Hỗ trợ viết spark job bằng cú pháp SQL
- Dễ dàng tích hợp với các công cụ báo cáo như: Business Intelligence, Analytics, Data Integration Tools
