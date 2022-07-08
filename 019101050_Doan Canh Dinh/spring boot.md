# Spring Boot

## Spring Boot 

![Image](https://user-images.githubusercontent.com/107390350/173716162-24ab7e6a-7093-4872-893e-cb4b1cd78b66.png)

Spring Boot là một dự án phát triển bởi JAV (ngôn ngữ java) trong hệ sinh thái Spring framework. Nó giúp cho các lập trình viên chúng ta đơn giản hóa quá trình lập trình một ứng dụng với Spring, chỉ tập trung vào việc phát triển business cho ứng dụng.

Để phát triển một ứng dụng web cơ bản HelloWorld sử dụng Spring framework bạn sẽ cần ít nhất 5 công đoạn sau;

Tạo một project sử dụng Maven với các dependency cần thiết của Spring MVC và Servlet API.
Một tập tin web.xml để khai báo DispatcherServlet của Spring MVC.
Một tập tin cấu hình của Spring MVC.
Một class Controller trả về một trang “Hello World” khi có request đến.
Cuối cùng là phải có một web server dùng để triển khai ứng dụng lên chạy.
Trong các công đoạn này, chỉ có công đoạn tạo một class Controller thì có thể khác cho các ứng dụng khác nhau vì mỗi ứng dụng có một yêu cầu khác nhau. Còn các công đoạn khác thì như nhau.

Giờ đây với Spring Boot, chúng ta có thể tạo dự án Spring một cách nhanh chóng và cấu hình cũng đơn giản dùng Sublime Text để phát triển luôn khỏi cần cài đặt eclipse hay netbean nặng.

## Các ưu điểm của Spring Boot

1.Tạo các ứng dụng Spring độc lập.

2.Nhúng trực tiếp Tomcat, Jetty hoặc Undertow (không cần phải deploy ra file WAR)

3.Các starter dependency giúp việc cấu hình Maven đơn giản hơn.

4.Tự động cấu hình Spring khi cần thiết.

5.Không sinh code cấu hình và không yêu cầu phải cấu hình bằng XML …

##  Ưu điểm của Spring Boot

1.Phát triển các ứng dụng dựa trên Spring một cách tiết kiệm thời gian và dễ dàng.

2.Tự động cấu hình tất cả các components cho một ứng dụng Spring cấp sản xuất.

3.Các máy chủ nhúng được tạo sẵn (Tomcat, Jetty và Undertow), dẫn đến việc triển khai ứng dụng được tăng tốc và hiệu quả hơn.

4.Điểm cuối HTTP, cho phép nhập các tính năng bên trong ứng dụng như chỉ số, tình trạng sức khỏe, v.v.
Không có cấu hình XML.

5.Nhiều lựa chọn bổ sung, hỗ trợ nhà phát triển làm việc với cơ sở dữ liệu được nhúng và trong bộ nhớ.

6.Dễ dàng truy cập cơ sở dữ liệu và các dịch vụ hàng đợi như MySQL, Oracle, MongoDB, Redis, ActiveMQ và các dịch vụ khác.

7.Tích hợp trơn tru với hệ sinh thái Spring.

8.Cộng đồng lớn và rất nhiều hướng dẫn, tạo điều kiện cho giai đoạn làm quen.

9.Giảm thiểu thời gian phát triển code, tăng hiệu suất phát triển chung của cả dự án.
Dễ dàng tích hợp các mô-đun liên quan như Sping-MVC, Spring Data, Spring Sercurity, Spring Cloud,v.v…

10.Nó cung cấp các HTTPs servers như Tomcat, Jety,.. để phát triển, kiểm thử, deploy một cách dễ dàng.

11.Cung cấp công cụ CLI(Command Line Interface) cho việc phát triển và test ứng dụng nhanh chóng từ command line

12.Ngoài ra còn có nhiều plugins để phát triển nhanh chóng bằng các công cụ như Build như Maven hoặc Gradle.

## Nhược điểm của Spring Boot

1.Thiếu kiểm soát. Do style cố định, Spring Boot tạo ra nhiều phụ thuộc không được sử dụng dẫn đến kích thước tệp triển khai lớn.

2.Quá trình chuyển đổi dự án Spring cũ hoặc hiện có thành các ứng dụng Spring Boot nhiều khó khăn và tốn thời gian.

3.Không thích hợp cho các dự án quy mô lớn. Hoạt động liên tục với các microservices, theo nhiều nhà phát triển, Spring Boot không phù hợp để xây dựng các ứng dụng nguyên khối.

## Lợi ích khi dùng spring boot 

Tại vì những lợi ích mà nó mang lại :

1. Giúp tạo được ứng dụng độc lập dựa trên Spring, có thể tự chạy được  java – jar.

2.Có ít cấu hình, có khả năng tự động cấu hình lại Spring khi cần, từ đó giúp các thành viên có thể tiết kiệm thời gian viết code và tăng thêm năng suất.

3.Giữ đầy đủ các tính năng của Spring Framework.

4.Spring boot không yêu cầu cấu hình XML và không sinh code cấu hình.

5.Không cần phải triển khai file WAR mà thực hiện nhúng trực tiếp các ứng dụng server.

6.Giúp cung cấp nhiều plugin.

## Spring boot  được áp dụng trong microservices 

Spring Boot đã trở thành một yếu tố không thể thiếu của hệ sinh thái Java, cung cấp một bộ công cụ hiệu quả và có thể mở rộng để xây dựng các ứng dụng Spring với kiến trúc microservices. Do thiết lập mặc định cho các bài kiểm tra đơn vị và tích hợp, nó cho phép các nhà phát triển tận hưởng quá trình triển khai và phát triển được tăng tốc. Hơn nữa, Spring Boot giúp các nhà phát triển xây dựng các ứng dụng mạnh với cấu hình rõ ràng và an toàn mà không tốn nhiều thời gian và công sức để có thêm kiến thức về Spring.