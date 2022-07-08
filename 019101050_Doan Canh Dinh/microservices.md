# GIỚI THIỆU Microservices 

## Microservices 

Là tên gọi của các dịch vụ nhỏ thuộc dạng tách biệt đại diện cho 1 phần nhỏ tương ứng bên trong các Business domain của lập trình viên. Với kiến thức Monolithic thì bạn sẽ sở hữu một server lớn với khả năng chịu mọi trách nhiệm giải quyết hầu hết các requests. Và việc này sẽ gây ra khá nhiều khó khăn trên các phương tiện đối với tất cả requests. 
Chính vì vậy, Microservices được xem như giải pháp có thể cân bằng được tất cả các traffic dựa theo yêu cầu của doanh nghiệp. Và nếu như bạn đang nhận một lượng lớn các thanh toán thì hầu hết bạn sẽ có thể scale up thiết bị thanh toán và giữ cho các dịch vụ nằm ở mức sử dụng 1 lượng nhỏ hơn so với các services.

## Mục đích sử dụng Microservices 

1.Trong kiến trúc Microservices, các service (dự án) tồn tại độc lập nhau về xử lý (process), lưu trữ (database) và request (client/server model)

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107390350/173478197-407c1a20-bab3-4203-aeb6-c0d4c6dee01b.png)

2.Employee service (sử dụng table tc_employee)
Store service (sử dụng table tc_store)
Inventory service (sử dụng table tc_warehouse)
Order service (sử dụng table tc_order). Trong đó table tc_order chỉ chứa khóa ngoại – tức ID của Nhân viên, ID của cửa hàng, ID của nhà kho theo đúng tinh thần thiết kế chuẩn hóa database.

##  Ưu điểm khi dùng Microservices

1.Microservices cho phép dễ dàng continuous delivery và deployment các ứng dụng lớn và phức tạp hơn. 

2.Có thể cải thiện khả năng bảo trì: bởi vì các service tương đối nhỏ nên dễ hiểu và dễ thay đổi hơn. 

3.Có khả năng testing dễ dàng: nhờ các services nhỏ

4.Có thể triển khai tốt hơn: các services thường rất dễ cho việc triển khai độc lập. 

5.Cho phép các services được phát triển nhanh chóng bởi những team khác nhau. Khi đó, mỗi team đều sẽ được phát triển và thử nghiệm để triển khai cũng như mở rộng được quy mô của dịch vụ của mình một cách độc lập nhất với tất cả các team.

6.Nếu như có lỗi xảy ra trong một service thì chỉ có service đó bị ảnh hưởng và các service khác sẽ thực hiện xử lý các yêu cầu cần thiết. Trong khi đó, thì mỗi một thành phần nếu như hoạt động sai của kiến trúc một khối thì nó sẽ làm ảnh hưởng đến toàn bộ hệ thống. 

7.Lập trình viên có thể thay đổi dễ dàng bằng cách sử dụng công nghệ mới khi triển khai các service. Tương tự như khi có thay đổi lớn thì các service đều có thể thực hiện và bạn dễ dàng thay đổi được công nghệ hơn. 

##  Nhược điểm khi dùng Microservices

1.Bởi vì các nhà phát triển thường xuyên phải đối phó với sự phức tạp khi tạo ra một hệ thống phân tán.

2.Cần phải implement việc communication giữa các inter-services.

3.Handle partial failure rất phức tạp bởi vì luồng xử lý cần phải đi qua nhiều service khác nhau.

4.Khi thực hiện các requests trải rộng trên nhiều service khó khăn thì điều này cần đòi hỏi sự phối hợp giữa các team. 

5.Thường rất khó khăn trong việc đảm bảo toàn vẹn cho CSDL nếu như triển khai theo các cấu trúc cơ sở dữ liệu dạng phân vùng. 

6.Việc triển khai và quản lý microservices nếu như làm thủ công theo cách làm với ứng dụng thì sẽ rất phức tạp.

7.Lập trình viên cần phải xử lý các sự cố kết nối chậm, lỗi nếu như thông điệp không được gửi hoặc nếu như thông điệp được gửi đến nhiều đích đến vào các thời điểm khác nhau. 

## Sự khác biệt giữa kiến trúc Microservices với kiến trúc Monolithic 

 Monolithic có những tính chất và ưu nhược điểm như:

Tính chất : Kiến trúc một khối là mẫu thiết kế được dùng nhiều nhất trong giới lập trình web hiện nay bởi tính đơn giản của nó khi phát triển và khi deploy. Mặc dù mỗi ứng dụng sẽ được triển khai theo những cách khác nhau, nhưng nhìn chung thì khi ứng dụng được lập trình theo kiến trúc một khối, kết quả thường đạt được như sau:

1. Nó có thể hỗ trợ nhiều loại client như browser hay các app native trên cả desktop và mobile.

2.Nó có thể expose API cho bên thứ ba.

3.Nó có thể tích hợp với các ứng dụng khác thông qua REST/SOAP web service hoặc các message queue.

4.Nó có thể xử lý các request dạng HTTP, thực hiện logic nghiệp vụ, truy cập cơ sở dữ liệu và có thể trao đổi dữ liệu với các hệ thống khác.

5.Nó có thể chạy trên các container như Tomcat, JBoss,..

6.Nó có thể scale theo chiều ngang (vertical scalability) bằng cách tăng sức mạnh của phần cứng hoặc scale theo chiều dọc (horizontal scalability) bằng cách load balancers.

Về ưu điểm thì Monolithic có những ưu điểm sau:

1.Dễ phát triển vì các stack công nghệ thống nhất ở tất cả các layer.

2.Dễ test do toàn bộ project được đóng gói trong một package nên dễ dàng chạy test integrantion và test end-to-end.

3.Deploy đơn giản và nhanh chóng nếu bạn chỉ có một package để bận tâm.

4.Dễ scale vì chúng ta có thể có nhiều instance cho load banlancer.

5.Yêu cầu team size nhỏ cho việc maintain app.

6.Team member có thể chia sẻ ít nhiều về skill.

7.Tech stack đơn giản và đa số là dễ học.

8.Phát triển ban đầu nhanh hơn do đó có thể đem sale hoặc marketing nhanh hơn.

9.Yêu cầu cơ sở hạ tầng đơn giản. Thậm chí một container đơn giản cũng đủ để chạy ứng dụng.

Về ưu điểm thì Monolithic có những nhược điểm sau:

1.Các component được liên kết chặt chẽ với nhau dẫn đến side effect không mong muốn như khi thay đổi một component ảnh hưởng đến một component khác.

2.Theo thời gian thì project trở nên phức tạp và lớn dần. Các tính năng mới sẽ mất nhiều thời gian hơn để phát triển và tái cấu trúc các tính năng hiện có sẽ nhiều khó khăn hơn.
Toàn bộ ứng dụng cần được triển khai lại cho bất kỳ thay đổi nào.

3.Không hề dễ để hiểu project do các module liên quan chặt chẽ lẫn nhau. Một issue nhỏ cũng có thể làm chết toàn bộ ứng dụng.

4.Áp dụng công nghệ mới khó khăn vì toàn bộ ứng dụng phải thay đổi. Do đó nhiều ứng dụng một khối thường phụ thuộc một công nghệ cũ và lỗi thời.

5.Các service quan trọng không thể scale riêng dẫn đến lãng phí tài nguyên vì toàn bộ ứng dụng phải scale theo.

6.Các ứng dụng một khối lớn sẽ có thời gian khởi động lâu và tốn tài nguyên CPU cũng như bộ nhớ.

7.Các team tham gia vào dự án phải phụ thuộc lẫn nhau và tất khó để mở rộng quy mô team.

Kết luận sự khác biệt giữa kiến trúc Microservices với kiến trúc Monolithic là 

Microservice là tốt, nhưng không phải cho tất cả các loại ứng dụng. Mẫu này hoạt động tuyệt vời để phát triển các ứng dụng và hệ thống phức tạp. Cân nhắc chọn kiến trúc microservice khi  có nhiều nhóm có kinh nghiệm và khi ứng dụng đủ phức tạp để chia nó thành các dịch vụ. Khi ứng dụng lớn và cần phải linh hoạt và có thể mở rộng, microservice có lợi.

### Thiết kế phần mềm theo kiến trúc Microservice

1.Mỗi microservice nên có một database riêng biệt.

2.Giữ source code của microservice ở mức hợp lý.

3.Tạo build script cho mỗi microservice.

4.Triển khai mỗi microservice bên trong một app (docker container).

5.Stateless server.