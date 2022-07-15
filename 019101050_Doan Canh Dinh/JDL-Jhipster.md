# Chương 5: JDL

## 1. Khái niệm JDL

JDL (JHipster Domain Language) là ngôn ngữ miền dành riêng cho JHipster, nơi người dùng có thể mô tả tất cả các ứng dụng, triển khai, thực thể và các mối quan hệ của chúng trong một tệp duy nhất (hoặc nhiều hơn một) với cú pháp thân thiện với người dùng.

## 2. Tổng quát về JDL

Người dùng có thể sử dụng JDL-Studio trực tuyến của chúng tôi hoặc một trong các plugin tiện ích mở rộng JHipster IDE, có sẵn cho:

- Eclipse
- Visual studio code

Để tạo tệp JDL và trực quan hóa UML của nó. Người dùng cũng có thể tạo và xuất hoặc chia sẻ URL của mô hình JDL của người dùng.

Điều này có thể được sử dụng để thay thế cho việc sử dụng trình tạo phụ thực thể và là cách tiếp cận được khuyến nghị. Ý tưởng là việc quản lý các mối quan hệ bằng cách sử dụng công cụ trực quan sẽ dễ dàng hơn nhiều so với các câu hỏi và câu trả lời cổ điển của Yeoman.

Dự án JDL có sẵn trên GitHub, nó là một dự án Mã nguồn mở giống như JHipster (Giấy phép Apache 2.0). Nó cũng có thể được sử dụng như một thư viện nút để phân tích cú pháp JDL.

## 3. Các ứng dụng

#### 3.1. Cú pháp:

Việc khai báo đơn được thực hiện như sau:

![image](https://user-images.githubusercontent.com/107389856/177963471-2c6de657-4529-444f-a770-bcbc3b1a0d06.png)

- Các khóa / giá trị cấu hình ứng dụng được chỉ định bên dưới config(phải ở bên trong application)
- Có thể có 0, 1 hoặc bất kỳ tùy chọn ứng dụng nào người dùng muốn (miễn là chúng hợp lệ)
- Các thực thể sẽ được tạo bên trong ứng dụng được liệt kê thông qua entities, đây là cách được khuyến nghị để tạo các thực thể trong ứng dụng.
- Điều này có thể được bỏ qua nhưng việc tạo các thực thể bên trong ứng dụng sẽ yêu cầu thực hiện điều đó:từ một tệp JDL khác bên trong ứng dụng hoặc với CLI.
- Từ entities khóa là tùy chọn: người dùng có thể bỏ qua nó, nhưng mọi thực thể trong tệp JDL sẽ được tạo bên trong ứng dụng.
#### 3.2. Các tùy chọn trong ứng dụng

Khai báo tùy chọn ( dto,, v.v. service) skipServerđược hỗ trợ trong các ứng dụng JDL, nhưng với một số quy tắc.

Giả sử chúng ta có tệp JDL này:
![image](https://user-images.githubusercontent.com/107389856/177963784-1cbb28d4-28ea-420e-819e-1158fe1e69fe.png)

Trong mẫu này, chúng ta có thể thấy một số điều:
A, B, C, D, E and F có 6 thực thể được khai báo trong tệp JDL: chúng tôi có 3 ứng dụng:app1, app2 and app3 app1 sử dụng A, B and C app2 sử dụng C and D app3 sử dụng E( * except A, B, C, D, F) Mỗi ứng dụng này khai báo các tùy chọn và một tùy chọn chung cũng được khai báo. app1 sử dụng dto cho A, B and C app2 sử dụng paginate cho C(vì có một ngoại lệ) app3 sử dụng service cho E Toàn cầu cũng sử dụng pagination(cho mọi thực thể). Đây là cách tệp được tạo:

app1 A: sẽ sử dụng paginate with infinite-scroll (tùy chọn chung không bị ghi đè bởi tùy chọn cục bộ) và dto with mapstruct B: sẽ sử dụng các tùy chọn tương tự C: cũng sẽ sử dụng các tùy chọn tương tự app2: C: sẽ sử dụng paginate with pagination (và không infinite-scroll, vì cái cục bộ được ưu tiên hơn) D: sẽ sử dụng paginate with infinite-scroll như tùy chọn trước đó không bao gồm D app3: E: sẽ paginate with infinite-scrollvàservice E with serviceClass Ví dụ này minh họa nguyên tắc đổ bóng . Các tùy chọn chung được hỗ trợ và sẽ được sử dụng bởi mọi ứng dụng đã khai báo trừ khi các tùy chọn cũng được khai báo trong các ứng dụng.

Cũng lưu ý đoạn mã này được lấy từ mẫu trước đó trong app3:

entities * except A, B, C, D, F service * with serviceClass

Về cơ bản, điều này có nghĩa là app3 sẽ chỉ sử dụng E và các thực thể của ứng dụng sẽ sử dụng service tùy chọn, có nghĩa là E và không A to F.

Cuối cùng, F thực thể không có trong bất kỳ ứng dụng nào và thực thể này sẽ không được tạo vì điều đó.

#### 3.3. Các ví dụ

Ví dụ cơ bản Permalink to "Basic example"

![image](https://user-images.githubusercontent.com/107389856/177964499-85829a6e-134c-4630-9ed4-9e4bff1f9239.png)

Nhiều ứng dụng

![image](https://user-images.githubusercontent.com/107389856/177964551-a9d6f1a3-a152-4163-b53e-83a040ad1615.png)

Với các thực thể

![image](https://user-images.githubusercontent.com/107389856/177964666-fb93ead7-3279-4bfb-a76a-e3fac4b5b92e.png)

Với các tùy chọn

![image](https://user-images.githubusercontent.com/107389856/177964761-2476e592-3887-4b5c-91b2-46faba05891d.png)

#### 3.4. Toàn bộ bảng phân tích ví dụ

![image](https://user-images.githubusercontent.com/107389856/177964871-5ab0c887-4e21-42be-812f-4e115f70c185.png)

Bây giờ, một số điều sẽ xảy ra khi tạo các ứng dụng và thư mục này:

Bốn ứng dụng sẽ được tạo:

myMonolith trong ./myMonolith, với cổng máy chủ 8080 myGateway trong ./myGateway, với cổng máy chủ 9042 microserviceA trong ./microserviceA, với cổng máy chủ 8081

Mặc dù chúng tôi không chỉ định cổng máy chủ, JHipster đặt một cổng theo mặc định.

Đối với microservices, mặc định là 8081.

Đối với cổng và đá nguyên khối, nó 8080 microserviceB trong ./microservice B với cổng máy chủ 8082.

Bốn thực thể sẽ được tạo

A và Btrong nguyên khối

C và Dcả trong cửa ngõ

C trong microservice đầu tiên

D trong microservice thứ hai

Tùy microservice chọn này ngầm hiểu cho C và D

Vì chúng được tạo trên hai microservices nên tùy chọn này sẽ được đặt theo mặc định.

Các tùy chọn hoạt động giống như trước đây

Lưu ý rằng trình tạo đặt các giá trị mặc định nếu chúng không có (như databaseType). JHipster Core làm những điều tương tự cho người dùng.

Đối phó với microservices là một công việc gần như phức tạp, nhưng JDL cung cấp cho người dùng một số tùy chọn để xử lý các thực thể của người dùng khi người dùng thấy phù hợp. Với microservice with <MICROSERVICE_APP_NAME>người dùng, người dùng có thể chỉ định thực thể nào được tạo trong microservice nào.

Lấy ví dụ như thiết lập này:

![image](https://user-images.githubusercontent.com/107389856/177965374-52dc9505-dc6c-4849-adc1-4070625f2f9f.png)

Với hai ứng dụng JHipster ('firstMS' và 'secondMS'), đây là những gì người dùng sẽ nhận được nếu nhập tệp JDL trong hai ứng dụng:

Trong 'firstMS', các thực thể Avà Csẽ được tạo. Trong 'secondMS', các thực thể Bvà Csẽ được tạo. Cđược tạo cả hai vì nếu không có tùy chọn microservice chỉ định nơi thực thể này được tạo, nó sẽ được tạo ở mọi nơi.

Nếu người dùng quyết định nhập JDL này trong một ứng dụng nguyên khối, mọi thực thể sẽ được tạo (nguyên khối không có tùy chọn hạn chế trong JDL).

Lưu ý: nếu người dùng muốn tạo cùng một thực thể trong hai dịch vụ nhỏ khác nhau, người dùng có thể ghi hai tệp JDL thay vì cập nhật tệp JDL. Mỗi lần.

Ví dụ trước không thể được viết như thế này:

![image](https://user-images.githubusercontent.com/107389856/177965516-beae6444-f282-4486-9c14-fedc4656f9bd.png)

Đây là kết quả:

Trong 'firstMS', chỉ thực thể Csẽ được tạo Trong 'secondMS', các thực thể Bvà Csẽ được tạo. Đó là bởi vì, tại thời điểm phân tích cú pháp, nếu một tùy chọn trùng lặp với một tùy chọn khác, thì tùy chọn sau sẽ được ưu tiên hơn. người dùng cũng có thể tạo toàn bộ ngăn xếp microservice bằng JDL, hãy xem bài đăng trên blog này chẳng hạn.

#### 3.5. Các tùy chọn cấu hình ứng dụng có sẵn

Dưới đây là các tùy chọn ứng dụng được hỗ trợ trong JDL:

![image](https://user-images.githubusercontent.com/107389856/177965690-e0116dcc-c1d3-4e1f-82f0-d2b40780e7b2.png)

## 4. Entity

#### 4.1. Cú pháp

Việc khai báo thực thể được thực hiện như sau:

![image](https://user-images.githubusercontent.com/107389856/177965877-5b08e6f0-4880-4ed1-9169-2a0f746e1af4.png)

Tên của thực thể, tên của một trường của thực thể, loại trường được hỗ trợ JHipster, và như một tùy chọn: tài liệu của thực thể, các tùy chọn cho thực thể (xem Tùy chọn để có danh sách đầy đủ các tùy chọn có sẵn),

tên bảng cơ sở dữ liệu (nếu người dùng muốn chỉ định một cái gì đó khác mà tên được tính tự động từ tên thực thể), tài liệu của lĩnh vực này, các tùy chọn cho trường, các xác nhận cho trường.

Tuyên bố Blob JHipster cung cấp một sự lựa chọn tuyệt vời vì người ta có thể chọn giữa một loại hình ảnh hoặc bất kỳ loại nhị phân nào. JDL cho phép người dùng làm điều tương tự. Tạo một loại tùy chỉnh (xem DataType) bằng trình chỉnh sửa, đặt tên cho nó theo các quy ước sau:

AnyBlob hoặc Blob để tạo một trường thuộc loại nhị phân "bất kỳ"; ImageBlob để tạo một trường có nghĩa là một hình ảnh. TextBlob để tạo trường cho CLOB (văn bản dài). Và người dùng có thể tạo bao nhiêu DataTypes tùy thích.

Biểu thức chính quy Đây là một xác thực nhất định (chỉ có sẵn cho các loại Chuỗi) và cú pháp của nó là:

![image](https://user-images.githubusercontent.com/107389856/177966101-07d3d806-d077-4b2e-ab36-46b24c35cb16.png)

Hãy chia nhỏ nó ra:

pattern là từ khóa để khai báo xác thực regex (với dấu ngoặc đơn bình thường) /.../mẫu được khai báo bên trong hai dấu gạch chéo \chống chém không cần thiết phải thoát Bình luận Có thể nhận xét trong JDL cho các thực thể và trường, và sẽ tạo ra tài liệu (Javadoc hoặc JSDoc, tùy thuộc vào phần phụ trợ).

![image](https://user-images.githubusercontent.com/107389856/177966195-1e9c04ae-d668-49c4-a73b-9b87a7d5d3ca.png)

Những bình luận này sau đó sẽ được thêm vào dưới dạng bình luận Javadoc của JHipster. JDL sở hữu loại nhận xét riêng của nó:

// một bình luận bị bỏ qua / ** không phải là một bình luận bị bỏ qua * / Do đó, bất kỳ thứ gì bắt đầu bằng //đều được coi là nhận xét nội bộ cho JDL và sẽ không được tính là Javadoc. Xin lưu ý rằng các lệnh JDL Studio bắt đầu bằng #sẽ bị bỏ qua trong quá trình phân tích cú pháp.

Một dạng nhận xét khác là các nhận xét sau:

![image](https://user-images.githubusercontent.com/107389856/177966276-527e94e2-c4e8-406c-a3b3-dd407bf5dfb3.png)

Ở đây tên của A sẽ được nhận xét với My super field, B với My other super field.

Có, dấu phẩy không phải là bắt buộc nhưng sẽ khôn ngoan hơn nếu có chúng để không mắc lỗi trong mã. Nếu bạn muốn kết hợp dấu phẩy và nhận xét sau, hãy cẩn thận!

![image](https://user-images.githubusercontent.com/107389856/177966375-bde5bb31-ec90-4e0c-937c-e0bac1ba9339.png)

#### 4.2. Các loại trường và xác thực

![image](https://user-images.githubusercontent.com/107389856/177966613-60aa541d-4859-4b14-8617-06a7b95b8d76.png)

## 5. EnumsPermalink to " JHipster Domain Language (JDL) - Enums"

#### 5.1. Cú pháp 

Việc khai báo điều tra được thực hiện như sau:

![image](https://user-images.githubusercontent.com/107389856/177966773-9e81bffa-32c8-44f7-a6c4-b8be191df0a7.png)

Giá trị mục nhập liệt kê là bắt buộc Và các phím chữ hoa phải được sử dụng Giá trị mục nhập liệt kê là tùy chọn và phải được đặt bên trong dấu ngoặc đơn

## 6. Mối quan hệ

#### 6.1. Các kiểu quan hệ

Được đề cập sau relationship từ khóa.

Có bốn kiểu quan hệ:

- OneToOne
- OneToMany
- ManyToOne
- ManyToMany

Để biết thêm về các mối quan hệ và những gì có thể đạt được, bạn có thể truy cập trang dành riêng.

#### 6.2. Các phương pháp quan hệ

Cú pháp này thực sự hữu ích khi:

Bạn có nhiều mối quan hệ cùng loại.

Bạn không muốn mất thời gian tìm kiếm chúng trong (các) tệp JDL của mình.

#### 6.3. Cú pháp 

![image](https://user-images.githubusercontent.com/107389856/177967160-e7f565c5-6444-4f67-9333-c19b8712fd2b.png)

(OneToMany | ManyToOne| OneToOne | ManyToMany)là kiểu mối quan hệ của bạn.

- là tên của chủ sở hữu thực thể của mối quan hệ: nguồn.

- là tên của thực thể mà mối quan hệ đi đến: đích.

- là tên của trường có đầu kia là loại.

- là tên của trường sẽ hiển thị trong các hộp chọn (mặc định id:).

required trường được tiêm có được yêu cầu hay không. with jpaDerivedIdentifier có @MapsId được sử dụng cho liên kết hay không (chỉ áp dụng cho một đối một)

OneToMany

Tạo Car:

![image](https://user-images.githubusercontent.com/107389856/177967400-ad0805aa-c238-4561-865d-199448b94d63.png)

Điều tương tự cũng có thể đạt được bằng cách sử dụng JDL bên dưới:

![image](https://user-images.githubusercontent.com/107389856/177967458-a2d32da4-a59d-47b2-b3e4-80b722af1338.png)

ManyToOne

Điều này tương đương với mối quan hệ một-nhiều hai chiều sau khi đảo các cạnh trong tệp JDL:

![image](https://user-images.githubusercontent.com/107389856/177967531-aaaaa617-0596-4b33-8252-4f3e163f6848.png)

Thực hiện mối quan hệ đó vì hai lý do:

Theo quan điểm kinh doanh, bạn chỉ sử dụng các thực thể của mình theo cách này. Vì vậy, bạn không muốn có một API cho phép các nhà phát triển làm điều gì đó không có ý nghĩa.

Bạn có một mức tăng hiệu suất nhỏ khi sử dụng Owner thực thể.

Tạo Owner:

![image](https://user-images.githubusercontent.com/107389856/177967653-a8491177-5a22-459f-9a1f-d282c238e59f.png)

Trên giao diện người dùng ứng dụng Angular / React được tạo, bạn sẽ có một menu thả xuống Car để chọn Owner. Đây là JDL tương ứng:

![image](https://user-images.githubusercontent.com/107389856/177967725-4fc97853-d9bd-4a31-a5d1-88f7593c9f40.png)

OneToMany

Mối quan hệ một chiều một-nhiều có nghĩa là Ownercá thể có thể nhận được bộ sưu tập xe của nó, nhưng không phải ngược lại. Nó ngược lại với ví dụ trước.

![image](https://user-images.githubusercontent.com/107389856/177967816-c5382e61-8cbb-43b1-855d-040c5ae96c53.png)

Loại mối quan hệ này không được cung cấp theo mặc định trong JHipster vào lúc này, hãy xem # 1569 để biết thêm thông tin.
Bạn có hai giải pháp cho việc này:

Thực hiện ánh xạ hai chiều và sử dụng nó mà không cần sửa đổi: đây là cách tiếp cận được đề xuất của chúng tôi, vì nó đơn giản hơn nhiều

Thực hiện ánh xạ hai chiều, sau đó sửa đổi nó để biến nó thành ánh xạ một hướng:

Xóa thuộc tính “mappedBy” trên @OneToManychú thích của bạn
Tạo bảng tham gia bắt buộc: bạn có thể thực hiện mvn liquibase:diffđể tạo bảng đó, xem tài liệu về cách sử dụng Liquibase diff

Điều này không được hỗ trợ với JDL vì nó không có trong JHipster.

TwoOneToMany

Đối với ví dụ này, a Person có thể là chủ sở hữu của nhiều ô tô và cũng có thể là người điều khiển nhiều ô tô:

![image](https://user-images.githubusercontent.com/107389856/177967930-60f45cb5-4a1a-4448-a6e6-1aea745012b7.png)

Tạo Person thực thể, có hai mối quan hệ một-nhiều với Carthực thể:

![image](https://user-images.githubusercontent.com/107389856/177967959-d7f12393-1c07-4618-a461-adaaafc21b65.png)

Tạo Carthực thể, sử dụng cùng một tên quan hệ đã được định cấu hình trong Person thực thể:

![image](https://user-images.githubusercontent.com/107389856/177967988-bcdef774-4ab7-4225-bda6-9e5b70b449a8.png)

Điều tương tự cũng có thể đạt được bằng cách sử dụng JDL bên dưới:

![image](https://user-images.githubusercontent.com/107389856/177968223-1ae301b6-84b4-4b4d-8573-bf6dce4bdaaa.png)

ManyToMany

A Drivercó thể lái nhiều ô tô, nhưng một Carcan cũng có nhiều tài xế.

![image](https://user-images.githubusercontent.com/107389856/177968239-ab961fe7-b630-4438-9481-7b765f492532.png)

Tạo ra mặt không sở hữu của mối quan hệ, Drivervới mối quan hệ nhiều-nhiều:

![image](https://user-images.githubusercontent.com/107389856/177968255-d9d081d6-e176-44f8-b8b1-47b0a3d5f873.png)

Tạo Car, với mặt riêng của mối quan hệ nhiều-nhiều:

![image](https://user-images.githubusercontent.com/107389856/177968278-e6a95c14-cb12-47c0-aa0e-9cd6935c1dc3.png)

Điều tương tự cũng có thể đạt được bằng cách sử dụng JDL bên dưới

![image](https://user-images.githubusercontent.com/107389856/177968303-26d46546-8e7d-4557-a280-6bdb2a0de71f.png)

## 7. Triển khai

#### 7.1. Cú pháp

Khai báo triển khai được thực hiện như sau:

![image](https://user-images.githubusercontent.com/107389856/177968334-5bf9b8c5-04fa-4fe1-987f-46e0f8112170.png)

Các ví dụPermalink to "Examples"

![image](https://user-images.githubusercontent.com/107389856/177968382-67dbef97-0564-446c-b206-18925bffd54e.png)

Nhiều triển khai

![image](https://user-images.githubusercontent.com/107389856/177968420-6cd44343-8ca2-450e-b855-8d17be1ef3db.png)

Các tùy chọn triển khai có sẵnPermalink to "Available deployment options"

![image](https://user-images.githubusercontent.com/107389856/177968606-ac0ce4a1-92d7-4667-a6e8-12a98792aced.png)

Xử lý sự cố

Chúng tôi đã cố gắng giữ cho cú pháp thân thiện nhất có thể đối với các nhà phát triển. Bạn có thể làm những điều này với nó:

Khai báo các ứng dụng với các tùy chọn và thực thể của chúng,

Khai báo các thực thể với các thuộc tính của chúng,

Khai báo các mối quan hệ giữa chúng,

Và khai báo một số tùy chọn cụ thể của JHipster.
