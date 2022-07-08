# Chương 4: jHipster

## 1. Khái niệm jHipster

JHipster( viết tắt của Java Hipster ) là một phương pháp đơn giản để tạo ra một project xung quanh những công nghệ được ưa thích nhất với Spring technology, Angular/React và các microservices Spring.

- Server side xây dựng backend với công nghệ Spring Boot + Spring security.

![image](https://user-images.githubusercontent.com/107389856/174565126-e0d02950-83e3-4da5-af70-2f5c01b75c6d.png)

- Client side với những Framework mạnh mẽ.

![image](https://user-images.githubusercontent.com/107389856/174565258-ec967162-1958-4309-a6f0-73d80dd771d2.png)

- Deployment dự án dễ dàng.

![image](https://user-images.githubusercontent.com/107389856/174565379-b7a25904-d79a-4f53-a832-bc86e0853f7b.png)

## 2. Cách khởi tạo Monolithic và Microservices

#### B1: Cài đặt java, node.js, Git

Windows -> Run -> cmd

Kiểm tra java:

- java --version

Kiểm tra node js:

- node --version

![image](https://user-images.githubusercontent.com/107389856/174553288-207f80c8-53bd-47d2-b4f3-c295b09a31d3.png)

#### B2: Cài đặt Jhipster

Lệnh cài đặt sau khi cài java, node.js, git:

- npm install -g generator-jhipster

![image](https://user-images.githubusercontent.com/107389856/174553818-c8ba5351-ed98-4b32-b2b4-e1fd358a11cf.png)

Lệnh kiểm tra cài đặt npm:

- npm -version

![image](https://user-images.githubusercontent.com/107389856/174556415-dca1d2ae-9acc-48c7-b127-0b38aaedc58f.png)

#### B3: Khởi tạo kiến trúc

Cách tạo Monolithic

![image](https://user-images.githubusercontent.com/107389856/174552971-fc0ff004-080d-435a-adc1-c899e157a55f.png)

Cách tạo Microservices

![image](https://user-images.githubusercontent.com/107389856/174554904-23cf10ae-2c80-42d0-acd4-000808fa0e65.png)

## 3. Những câu hỏi cơ bản để khởi tạo project trong jhipster

![image](https://user-images.githubusercontent.com/107389856/174557813-7ffc1f0f-6605-403e-be69-b152a75a51bb.png)

- Lựa chọn kiến trúc: Microservices application

Microservices là một loại ứng dụng JHipster, không có giao diện người dùng (giao diện người dùng Angular phải được tạo trên một cổng) và hoạt động với JHipster Registry để được định cấu hình, phát hiện và quản lý.

- Tên project: CodeMicroservice
- Chọn port: 8081
- tên package: com.myapp.microservice
- Chọn máy chủ khám phá dịch vụ: Jhipster Registry

JHipster Registry là một ứng dụng thời gian chạy, sử dụng cấu trúc JHipster thông thường, trên đó tất cả các ứng dụng đăng ký và nhận cấu hình của chúng.

- Chọn xác thực: JWT authentication

JSON Web token (JWT) là một chuẩn mở (RFC 7519) định nghĩa một cách nhỏ gọn và khép kín để truyền một cách an toàn thông tin giữa các bên dưới dạng đối tượng JSON. Thông tin này có thể được xác minh và đáng tin cậy vì nó có chứa chữ ký số. JWTs có thể được ký bằng một thuật toán bí mật (với thuật toán HMAC) hoặc một public / private key sử dụng mã hoá RSA.

- Chọn database liên kết: MySQL
- Triển khai database: MySQL

MySQL là một hệ thống quản trị cơ sở dữ liệu mã nguồn mở (gọi tắt là RDBMS) hoạt động theo mô hình client-server. Với RDBMS là viết tắt của Relational Database Management System. MySQL được tích hợp apache, PHP. MySQL quản lý dữ liệu thông qua các cơ sở dữ liệu. Mỗi cơ sở dữ liệu có thể có nhiều bảng quan hệ chứa dữ liệu. MySQL cũng có cùng một cách truy xuất và mã lệnh tương tự với ngôn ngữ SQL.

- Chọn bộ nhớ đệm: Ehcache

Ehcache là một bộ đệm dựa trên tiêu chuẩn, mã nguồn mở để tăng hiệu suất, đơn giản hóa khả năng mở rộng và giảm tải cơ sở dữ liệu của người dùng. ehcache được sử dụng để cải thiện hiệu suất bằng cách giảm tải cho các tài nguyên bên dưới. nó cũng có thể được sử dụng để lưu vào bộ nhớ đệm máy chủ hoạt động ổn định, tính liên tục của ứng dụng và bộ nhớ đệm phân tán.

- Chọn thư viện maven hoặc gradle: maven

Maven là công cụ quản lý và thiết lập tự động 1 dự án phần mềm. Chủ yếu dùng cho các lập trình viên java, nhưng nó cũng có thể được dùng để xây dựng và quản lý các dự án dùng C#, Ruby, Scala hay ngôn ngữ khác.

- Chọn công nghệ: Angular

Angular là một javascript framework do google phát triển để xây dựng các Single Page Application (SPA) bằng JavaScript , HTML và TypeScript . Angular cung cấp các tính năng tích hợp cho animation , http service và có các tính năng như auto-complete , navigation , toolbar , menus ,… Code được viết bằng TypeScript , biên dịch thành JavaScript và hiển thị tương tự trong trình duyệt.

- Chọn ngôn ngữ App: English
- Chọn ngôn ngữ tải về: Vietnamese

Project được tạo ra trên hình theo các công nghệ:

- Backend: Spring Boot + Spring security

- Database: 

        - MySQL(production)

        - MySQL(development)

- Frontend: Bootstrap + SASS + Angular

## 4. Tác dụng của việc lựa chọn

Các lựa chọn trên giúp người dùng lựa chọn và sử dụng các công nghệ hiện đại theo ý người dùng để phát triển.

- Tạo ra một project nhanh chóng dễ sử dụng.
- Tạo Microservices Với JHipster.
- Tạo cổng API.
- Tạo thực thể.
- Thêm Logic kinh doanh.
- Thực hiện các cải tiến về giao diện người dùng.
- Cho phép HTML.
- Tạo một dịch vụ nhỏ.
- Tạo thực thể sản phẩm.
- Triển khai lên đám mây.

## 5. Tác dụng của công nghệ jHipster

- Một công cụ rất hữu ích giúp các người dùng có thể tạo ra 1 project java web một cách nhanh chóng và đầy đủ các chức năng cần thiết.
- Phía Backend người dùng thể dùng nhiều công nghệ như Spring boot, Spring Sercurity, Maven, Grandle,..
- Phía Frontend người dùng có thể dùng các framework như React, Angular, VueJs, ...
- Người dùng cũng có thể sử dụng nhiều loại cơ sở dữ liệu khác nhau cả Sql và NoSql như MySql, Cassandra, MongoDb,...
- Sau khi generate code người dùng còn có thể tùy chọn việc deloy code của người dùng lên server, Jhipster hỗ trợ nhiều cách khác nhau như: Docker, Aws, HeroKu, Google Cloud Flatform,...