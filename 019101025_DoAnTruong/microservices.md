# Chương 2: Microservices

## 1. Khái niệm của Microservices

Microservices là tên gọi của các dịch vụ nhỏ thuộc dạng tách biệt đại diện cho 1 phần nhỏ tương ứng bên trong các Business domain của lập trình viên. Với kiến thức Monolithic thì bạn sẽ sở hữu một server lớn với khả năng chịu mọi trách nhiệm giải quyết hầu hết các requests. Và việc này sẽ gây ra khá nhiều khó khăn trên các phương tiện đối với tất cả requests. 

## 2. Kiến trúc của microservices

Bên trong kiến trúc của Microservices thì các services sẽ tồn tại độc lập nhau về xử lý, lưu trữ và cả request. Và cấu trúc cụ thể của nó sẽ như hình sau: 

![Image](https://user-images.githubusercontent.com/107389856/173475379-a9a370fc-aac8-45fb-b170-4dd6dc637998.png)

Ví dụ như sau: nếu như người dùng cần xây dựng một hệ thống để bán hàng dựa trên Microservices thì giả giả sử đơn hàng sẽ cần tối thiểu 4 service với database độc lập như sau:

- Employee service (sử dụng table tc-employee)
- Store service (sử dụng table tc-store)
- Inventory service (sử dụng table tc-warehouse)
- Order service (sử dụng table tc-order)

## 3. Ưu điểm và hạn chế của microservices

#### 3.1. Ưu điểm của microservices

- Khi cần thay đổi một thành phần, thì chỉ cần sửa đổi, cập nhật và triển khai lại thành phần đó chứ không cần triển khai lại toàn bộ hệ thống.

- Dễ dàng mở rộng và tích hợp với các dịch vụ của bên thứ ba.

- Các microservice khởi động nhanh giúp quá trình phát triển, kiểm thử cũng nhanh hơn.

- Một microservice có thể được phát triển bởi một team nhỏ. Do vậy việc quản lý sẽ dễ dàng hơn.

- Dễ dàng thực hiện tự động tích hợp và tự động triển khai (CI-CD) bằng cách sử dụng một số công cụ như Jenkins, Hudson …

- Cho phép lập trình viên linh động hơn trong việc lựa chọn ngôn ngữ, công cụ và nền tảng để phát triển và triển khai các microservice (tuy nhiên trong một hệ thống, việc lựa chọn các ngôn ngữ khác nhau để phát triển các microservice không được khuyến khích)

- Mỗi microservice có kích thước nhỏ, giúp cho các lập trình viên dễ tiếp cận, đọc hiểu source code. Do vậy các thành viên mới tham gia team sẽ hòa nhập và đóng góp cho team nhanh hơn.

- Các microservice khởi động nhanh giúp quá trình phát triển, kiểm thử cũng nhanh hơn.

- Cô lập lỗi tốt hơn, khi một microservice bị lỗi và ngừng hoạt động thì các microservice khác vẫn có thể hoạt động bình thường. Với mô hình nguyên khối, một lỗi nhỏ có thể làm cả hệ thống ngừng hoạt động.

#### 3.2. Hạn chế của microservices

- Nhược điểm của kiến trúc microservice đến từ bản chất của hệ thống phân tán.

- Việc triển khai hệ thống microservice phức tạp hơn nhiều so với việc triển khai hệ thống nguyên khối.

- Các lập trình viên phải tốn nhiều công sức hơn để thực hiện phần giao tiếp giữa các microservice, với kiến trúc nguyên khối có khi họ chỉ cần gọi hàm để thực hiện việc này.

- Các microservice thường (nên) được triển khai bên trong docker container và giao tiếp với nhau qua REST API. Việc này làm hiệu năng của toàn bộ chương trình ứng dụng giảm xuống đáng kể do giới hạn tốc độ truyền tải của các giao thức và tốc độ mạng. Hơn nữa việc giao tiếp giữa các microservice có thể bị lỗi khi các kết nối bị lỗi.

- Cần tính toán kích cỡ của một microservice. Nếu một microservice quá lớn, bản thân nó trở thành một ứng dụng theo kiến trúc nguyên khối. Nếu một microservice quá nhỏ thì độ phức tạp của hệ thống tăng lên rất nhiều, làm cho hệ thống trở lên khó hiểu, lúc này việc quản lý giám sát và triển khai hệ thống sẽ khó khăn hơn.

- Khi ứng dụng ngày càng lớn lên, số lượng microservice ngày càng nhiều, các lập trình viên thường có xu hướng sử dụng sự hỗ trợ từ các công cụ mã nguồn mở, hoặc của bên thứ 3, việc sử dụng, tích hợp các công cụ này làm cho hệ thống khó kiểm soát và có thể bị dính các mã độc làm cho hệ thống kém an toàn.

## 4. Lợi ích của việc dùng microservices

- Source code rất tinh gọn: Bởi vì hệ thống được cấu thành từ các dự án nhỏ, và mỗi dự án đều rất đơn giản cũng như tập trung vào 1 hoặc 1 vài nghiệp vụ chính. Vì vậy, các code base và độ phức tạp của chúng đều không cao. Nhờ vậy, nó sẽ giúp mang lại tính gọn nhẹ, dễ bảo trì cũng như mở rộng hơn. 

- Bảo mật tối ưu cho source code: Khi nhân viên làm việc ở các dự án thì chỉ truy cập được vào một source code của dự án đó. 

- Được tồn tại độc lập: Bởi vì đây là 4 dự án khác nhau và chúng có thể có cách deploy riêng biệt và một service nào đó chết thì các service khác vẫn sẽ hoạt động một cách bình thường. 

- Scale hoàn toàn độc lập: Tùy thuộc vào nhu cầu sử dụng của hệ thống mà người dùng có thể scale riêng cho service đó. Có thể như service đơn hàng mà sử dụng thường xuyên nên chạy từ 2 đến 3 server để gia tăng performance. 

## 5. Sự khác biệt của kiến trúc microservices đối với các kiến trúc khác

#### 5.1. Sự khác biệt giữa Microservices và Monolithic

![Image](https://user-images.githubusercontent.com/107389856/173479161-4e645c2e-8dc4-4c1e-bfc7-d42783903312.png)

Biểu đồ ở trên giải thích sự khác biệt giữa kiến trúc Monolithic và kiến trúc Microservice rất rất đơn giản. Với kiến trúc Monolithic, bạn sẽ có 1 server lớn chịu trách nhiệm giải quyết tất cả các requests. Việc này sẽ gây khó khăn rất nhiều trên phương diện scale. Tuy nhiên, Microservices có thể cân bằng traffic theo nhu cầu của doanh nghiệp. Nếu đang nhận được 1 lượng lớn thanh toán, người dùng có thể scale up thiết bị thanh toán và giữ các dịch vụ khác ở mức sử dụng 1 lượng nhỏ hơn các services. Đây được gọi là scaling theo chiều ngang.

#### 5.2. Sự khác biệt giữa Microservices và API

- API là tập hợp các phương thức giao tiếp, truyền thông được xác định một cách rõ ràng các thành phần khác nhau.

- Microservices là một kiến trúc có khả năng phân tách các thành phần của một ứng dụng (nguyên khối) thành các dịch vụ nhỏ hơn và có khả năng tự vận hành.