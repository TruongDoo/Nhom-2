# Chương 3: Spring Boot

## 1. Khái niệm của Spring framework

Spring là một framework được ra đời để giúp các nhà phát triển có thể xây dựng hệ thống và chạy ứng dụng trên JVM một cách thuận tiện, đơn giản và nhanh chóng. Đây là một mã nguồn mở được phát triển và rất nhiều người sử dụng.

Spring framework là tập hợp gồm rất nhiều các dự án nhỏ khác nhau như: Spring MVC (sử dụng để xây dựng các ứng dụng trên nền tảng web), Spring Data, Spring Boot,…

## 2. Khái niệm của Spring Boot

Spring Boot là một dự án phát triển bởi JAV (ngôn ngữ java) trong hệ sinh thái Spring framework. Nó giúp cho các lập trình viên chúng ta đơn giản hóa quá trình lập trình một ứng dụng với Spring, chỉ tập trung vào việc phát triển business cho ứng dụng.

Spring Boot là một Java framework được phát triển bởi Pivital Team dựa trên Java framework mã nguồn mở để tạo ra các microservice, nhằm mục đích xây dựng các ứng dụng Spring độc lập một cách nhanh chóng và có khả năng thực thi ngay.

![Image](https://user-images.githubusercontent.com/107389856/173720707-c20bff87-2276-48f4-9c96-d64a829e72a7.png)

## 3. Ưu điểm và hạn chế của Spring Boot

#### 3.1. Ưu điểm của Spring Boot

- Spring Boot được phát triển nhằm giúp người không có nhiều kiến thức lập trình vẫn có thể xây dựng ứng dụng.
- Giảm thời gian lập trình xuống tối thiểu.
- Gia tăng năng suất trong lập trình.
- Spring Boot được phát triển tối ưu sao cho việc cấu hình XML trở nên đơn giản nhất trong Spring.
- Spring Boot được phát triển sao cho việc lập trình trở nên nhanh chóng và dễ dàng.
- Tạo ứng dụng một cách độc lập, có thể chạy trên cả nền tảng Java Web.
- Ngoài ra còn có nhiều plugins để phát triển nhanh chóng bằng các công cụ như Build như Maven hoặc Gradle.
- Cung cấp nhiều plugin.

#### 3.2. Hạn chế của Spring Boot

- Thiếu kiểm soát. Do style cố định, Spring Boot tạo ra nhiều phụ thuộc không được sử dụng dẫn đến kích thước tệp triển khai lớn.
- Quá trình chuyển đổi dự án Spring cũ hoặc hiện có thành các ứng dụng Spring Boot nhiều khó khăn và tốn thời gian.
- Không thích hợp cho các dự án quy mô lớn. Hoạt động liên tục với các microservices, theo nhiều nhà phát triển, Spring Boot không phù hợp để xây dựng các ứng dụng nguyên khối.

## 4. Tác dụng của Spring Boot

- Tự động cấu hình, có máy chủ nhúng, độc lập.
- Có nhiều tính năng vượt trội hơn các phần mềm khác.
- Code đơn giản, dễ học, dễ sử dụng.
- Dễ dàng tích hợp các mô-đun liên quan như Sping-MVC, Spring Data, Spring Sercurity, Spring Cloud,v.v…

## 5. Cách hoạt động Spring Boot trong microservices

Spring Boot cho phép xây dựng các ứng dụng sẵn sàng cho sản xuất một cách nhanh chóng và cung cấp các tính năng phi chức năng:

- Máy chủ nhúng dễ dàng triển khai với các vùng chứa.
- Nó giúp theo dõi các thành phần bội số.
- Nó giúp định cấu hình các thành phần bên ngoài.

Spring Boot đã trở thành một yếu tố không thể thiếu của hệ sinh thái Java, cung cấp một bộ công cụ hiệu quả và có thể mở rộng để xây dựng các ứng dụng Spring với kiến trúc microservices. Do thiết lập mặc định cho các bài kiểm tra đơn vị và tích hợp, nó cho phép các nhà phát triển tận hưởng quá trình triển khai và phát triển được tăng tốc. Hơn nữa, Spring Boot giúp các nhà phát triển xây dựng các ứng dụng mạnh với cấu hình rõ ràng và an toàn mà không tốn nhiều thời gian và công sức để có thêm kiến thức về Spring.

![Image](https://user-images.githubusercontent.com/107389856/173720969-f84d595c-967a-4fa6-9f6a-4847598240e5.png)