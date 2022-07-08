# Chương 1: Git

## 1. Khái niệm của Git

 GIT Là một hệ thống quản lý phiên bản phân tán(Distributed Version Control System-DVCS)ra đời vào năm 2005 và hiện được dùng rất phổ biến.So với các hệ thống quản lý phiên bản tập trung khi tất cả các mã nguồn và lịch sử thay đổi chỉ được lưu một nơi là máy chủ thì trong hệ thống phân tán, các máy không chỉ "check out" phiên bản mới nhất của các tập tin mà là sao chép(mirror)toàn bộ kho mã nguồn(repository).Như vậy, nếu như máy chủ ngừng hoạt động , thì người dùng hoàn toàn có thể lấy kho chứa từ bắt kì máy khách nào để sao chép ngược trở lại máy chủ để khôi phục lại toàn bộ hệ thống.Mỗi checkout thực sự là một bản sao đầy đủ của tất cả dữ liệu của kho chưá từ máy chủ.

## 2. Tác dụng của Git

- Lưu lại lịch sử các version của bất kỳ thay đổi nào của dự án. Giúp xem lại các sự thay đổi hoặc khôi phục (revert) lại sau này.

- Việc chia sẻ code trở nên dễ dàng hơn, lập trình viên có thể để public cho bất kỳ ai, hoặc private chỉ cho một số người có thẩm quyền có thể truy cập và lấy code về.

Vốn là một VCS nên Git cũng ghi nhớ lại toàn bộ lịch sử thay đổi của source code trong dự án. Lập trình sửa file, thêm dòng code tại đâu, xóa dòng code ở hàng nào…đều được Git ghi nhận và lưu trữ lại. 

## 3. Cách Git hoạt động

Sự khác biệt chính giữa Git và bất kỳ VCS nào khác (bao gồm Subversion…) là cách Git nghĩ về dữ liệu của nó.

Về mặt khái niệm, hầu hết các hệ thống khác đều lưu trữ thông tin dưới dạng danh sách các thay đổi dựa trên file. Các hệ thống này (CVS, Subversion, Perforce, Bazaar, v.v.) coi thông tin chúng lưu giữ dưới dạng một tập hợp các file và những thay đổi được thực hiện đối với mỗi file theo thời gian.

![Image](https://user-images.githubusercontent.com/107382675/173315605-66111018-514a-482e-ba2a-d06e81973cad.png)

## 4. Ưu điểm và hạn chế của GIT

#### 4.1. Ưu điểm của GIT

- Dễ sử dụng, thao tác nhanh, gọn, lẹ và rất an toàn.

- Sẽ dàng kết hợp các phân nhánh (branch), có thể giúp quy trình làm việc code theo nhóm đơn giản hơn rất nhiều.

- Chỉ cần clone mã nguồn từ kho chứa hoặc clone một phiên bản thay đổi nào đó từ kho chứa, hoặc một nhánh nào đó từ kho chứa là người dùng có thể làm việc ở mọi lúc mọi nơi.

- Deployment sản phẩm của người dùng một cách không thể nào dễ dàng hơn.

#### 4.2. Hạn chế của GIT

- Thuật toán SHA1 sự va chạm giá trị băm làm cho các pc thông thường làm hư hỏng một kho git.

- Sử dụng GIT trên hệ điều hành Microsoft Windows hơi phức tạp.

- Các tập tin không liên quan mà luôn luôn bị thay đổi, Git có thể chịu thiệt thòi hơn các hệ thống khác bởi vì các tập tin không được giữ dấu viết từng cái riêng lẻ.

## 5. Các thuật ngữ GIT

- Branch - Commit - Checkout - Fetch - Fork - Head - Index - Master - Merge - Origin - Pull - Push - Rebase - Remote - Repository - Stash - Tags - Upstream

## 6. Các lệnh GIT cơ bản
1. git config

Tác dụng : Để set user name và email của người dùng trong main configuration file.

Cách xài : Để kiểm tra tên và kiểu email trong cấu hình dùng git config -- global user.name và git config -- global user.email. Để set email hoặc tên mới git config -- global user.name = “Hải Nguyễn” và git config -- global user.email = “hainguyen@gmail.com”

2. git init

Tác dụng : Khởi tạo 1 git repository 1 project mới hoặc đã có.

Cách xài: git init trong thư mục gốc của dự án.

3. git clone

Tác dụng: Copy 1 git repository từ remote source.

Cách xài: git clone <:clone git url:>

4. git status

Tác dụng: Để check trạng thái của những file người dùng đã thay đổi trong thư mục làm việc. VD: Tất cả các thay đổi cuối cùng từ lần commit cuối cùng.

Cách xài: git status trong thư mục làm việc.

5. git add

Tác dụng: Thêm thay đổi đến stage/index trong thư mục làm việc.

Cách xài: git add

6. git commit

Tác dụng: commit nghĩa là một action để Git lưu lại một snapshot của các sự thay đổi trong thư mục làm việc. Và các tập tin, thư mục được thay đổi đã phải nằm trong Staging Area. Mỗi lần commit nó sẽ được lưu lại lịch sử chỉnh sửa của code kèm theo tên và địa chỉ email của người commit. Ngoài ra trong Git người dùng cũng có thể khôi phục lại tập tin trong lịch sử commit của nó để chia cho một branch khác, vì vậy người dùng sẽ dễ dàng khôi phục lại các thay đổi trước đó.

Cách dùng: git commit -m ”Đây là message, người dùng dùng để note những thay đổi để sau này dễ dò lại”

7. git push/ git pull

Tác dụng: Push hoặc Pull các thay đổi đến remote. Nếu người dùng đã added và committed các thay đổi và người dùng muốn đẩy nó lên hoặc remote của người dùng đã update và người dùng apply tất cả thay đổi đó trên code của mình.

Cách dùng: git pull <:remote:> <:branch:> and git push <:remote:> <:branch:>

8. git branch

Tác dụng: liệt kê tất cả các branch (nhánh).

Cách dùng: git branch hoặc git branch -a

9. git checkout

Tác dụng: Chuyển sang branch khác

Cách dùng: git checkout <: branch:> hoặc ** _ git checkout -b <: branch:> nếu người dùng muốn tạo và chuyển sang một chi nhánh mới.

10. git stash

Tác dụng: Lưu thay đổi mà người dùng không muốn commit ngay lập tức.

Cách dùng: git stash trong thư mục làm việc của người dùng.

11. git merge

Tác dụng: Merge 2 branch lại với nahu.

Cách dùng: Chuyển tới branch người dùng muốn merge rồi  dùng git merge <:branch_ban_muon_merge:>

12. git reset

Tác dụng: Người dùng đã đưa một tập tin nào đó vào Staging Area nhưng bây giờ người dùng muốn loại bỏ nó ra khỏi đây để không phải bị commit theo.

Cách dùng: git reset HEAD tên_file

13. git remote

Tác dụng: Để check remote/source người dùng có hoặc add thêm remote

Cách dùng: git remote để kiểm tra và liệt kê. Và git remote add <: remote_url:> để thêm.

14. git add

Tác dụng: Để đưa một tập tin vào Staging Area

Cách dùng: git add tên_file hoặc muốn thêm hết file của thư mục thì git add all

## 7. Sự khác biệt của GIT và các phần mềm khác

Điểm khác biệt quan trọng giữa Git và gần như tất cả các VCS khác. Nó khiến Git phải xem xét lại hầu hết mọi khía cạnh của kiểm soát phiên bản mà hầu hết các hệ thống khác đã sao chép từ thế hệ trước. Điều này làm cho Git giống như một hệ thống tệp nhỏ với một số công cụ cực kỳ mạnh mẽ được xây dựng trên nó, thay vì chỉ đơn giản là một VCS.

## 8. Khi sử dụng GIT

- Lưu lại được các phiên bản khác nhau của mã nguồn dự án phần mềm.

- Khôi phục lại mã nguồn từ 1 phiên bản bất kỳ.

- Dễ dàng so sánh của các phiên bản.

- Phát hiện được ai đã sửa phần nào làm phát sinh lỗi.

- Khôi phục lại tập tin bị mất.

- Dễ dàng thử nghiệm, mở rộng tính năng của dự án mà không làm ảnh hưởng đến phiên bản chính (master branch).

- Giúp phối hợp thực hiện dự án trong một nhóm 1 cách hiệu quả.

## 9. Khi không sử dụng GIT

- Không khôi phục được mã code lỡ xóa gây ra lỗi.

- Không quản lý được những người đã sửa code làm phát sinh lỗi

- Không khôi phục được tập tin đã bị mất.

- Khả năng phối hợp dự án trong nhóm bị hạn chế.

## 10. Cách sử dụng GIT

#### 10.1. B1: Tạo tài khoản GitHub

![Image](https://user-images.githubusercontent.com/107382675/173311849-7d286b02-3547-407d-a44a-b53d2495219f.png)

Để tạo tài khoản của người dùng, người dùng cần truy cập trang web của GitHub và điền vào mẫu đăng ký.

#### 10.2. B2: Cài đặt Git

Bây giờ chúng ta cần cài đặt các công cụ của Git trên máy tính. Chúng ta sẽ sử dụng CLI để liên lạc với GitHub.

Đối với Ubuntu:

Đầu tiên, cập nhật các gói của người dùng.
- sudo apt update

Tiếp theo, cài đặt Git và GitHub với apt-get
- sudo apt-get install git

Cuối cùng, xác minh rằng Git đã được cài đặt đúng
- git –version

Chạy các lệnh sau với thông tin của người dùng để đặt tên người dùng và email mặc định khi người dùng sẽ lưu công việc của mình.

- git config –global user.name “MV Thanoshan”

- git config –global user.email “example@mail.com”

#### 10.3. B3: Cách sử dụng Git

1. Cách thứ 1: Tạo kho lưu trữ, sao chép nó vào pc của người dùng và làm việc với nó.

Tạo một kho lưu trữ mới bằng cách nhấp vào nút Kho lưu trữ mới của Wikipedia trên trang web GitHub.

![Image](https://user-images.githubusercontent.com/107382675/173312121-da4ea5a0-24ff-43d0-9941-954f247d446d.png)

Chọn tên cho kho lưu trữ đầu tiên của người dùng, thêm một mô tả nhỏ, đánh dấu vào ô ‘Khởi tạo kho lưu trữ này với README’ và nhấp vào nút Tạo kho lưu trữ.

![Image](https://user-images.githubusercontent.com/107382675/173312279-72bcd828-7ad6-4e1d-a339-b8bf801a04d0.png)

Kho GitHub đầu tiên của người dùng được tạo.

Nhiệm vụ đầu tiên của người dùng là lấy một bản sao của kho lưu trữ vào máy tính của mình. Để làm được điều đó, người dùng cần phải sao chép lại kho lưu trữ trên máy tính của người dùng.

Để sao chép một kho lưu trữ có nghĩa là người dùng đang lấy một kho lưu trữ trên máy chủ và sao chép nó vào máy tính của người dùng – giống như tải xuống. Trên trang kho lưu trữ, người dùng cần lấy địa chỉ HTTPS.

![Image](https://user-images.githubusercontent.com/107382675/173312470-1204e5b4-324c-4c3c-9177-e0bb07166734.png)

Khi người dùng có địa chỉ của kho lưu trữ, người dùng cần sử dụng terminal của mình. Sử dụng lệnh sau trên terminal của người dùng. Khi người dùng đã sẵn sàng, người dùng có thể nhập lệnh này:

    - git clone [HTTPS ADDRESS]

Lệnh này sẽ tạo một bản sao cục bộ của kho lưu trữ tại địa chỉ đã cho.

![Image](https://user-images.githubusercontent.com/107389856/173522116-dd2c1d13-6691-430a-b504-1a8a36a80247.png)

Thông báo đầu ra của lệnh git clone bản sao

Bây giờ, kho lưu trữ của người dùng là trên máy tính của người dùng. Người dùng cần di chuyển trong nó bằng lệnh sau.

    - cd [NAME OF REPOSITORY]

Như người dùng có thể thấy trong hình trên, tên kho lưu trữ của người dùng là tên My- GitHub-Project, và lệnh này đã đưa người dùng đến thư mục cụ thể đó.

*LƯU Ý: Khi người dùng sao chép, Git sẽ tạo một kho lưu trữ trên máy tính của người dùng. Nếu người dùng muốn, người dùng có thể truy cập dự án của mình bằng giao diện người dùng máy tính thay vì sử dụng lệnh ‘cd’ trên terminal.

Bây giờ, trong thư mục đó, chúng ta có thể tạo các tệp, làm việc với chúng và lưu chúng cục bộ. Để lưu chúng ở một nơi xa xôi – như GitHub – chúng ta đã thực hiện một quy trình gọi là commit. Để làm điều này, quay trở lại terminal của người dùng. Nếu người dùng đã đóng nó, như người dùng đã nói trước đây, hãy sử dụng lệnh ‘cd’.

    - cd [NAME OF REPOSITORY]

Bây giờ, trong terminal, người dùng đang ở trong thư mục kho lưu trữ của người dùng. Có 4 bước trong một commit: ‘status’, ‘add’, ‘commit’ và ‘push’. Tất cả các bước sau đây phải được thực hiện trong dự án của người dùng. Chúng ta hãy đi qua từng cái một.

‘status’: Điều đầu tiên người dùng cần làm là kiểm tra các tập tin người dùng đã sửa đổi. Để làm điều này, người dùng có thể gõ lệnh sau để làm cho một danh sách các thay đổi xuất hiện.

    - git status

![Image](https://user-images.githubusercontent.com/107389856/173522836-8503e5e4-ba38-4f27-902a-0bf982c40b22.png)

‘add’: Với sự trợ giúp của danh sách thay đổi, người dùng có thể thêm tất cả các tệp người dùng muốn tải lên bằng lệnh sau,

    - git add [FILENAME] [FILENAME] […]

Trong trường hợp của chúng ta, chúng ta sẽ thêm một tệp HTML đơn giản.

    - git add sample.html 

‘commit’: Bây giờ chúng ta đã thêm các tệp mà chúng ta chọn, chúng ta cần viết một thông điệp để giải thích những gì chúng ta đã làm. Thông báo này có thể hữu ích sau này nếu chúng ta muốn kiểm tra lịch sử thay đổi. Dưới đây là một ví dụ về những gì chúng ta có thể đặt trong trường hợp của chúng ta.

    - git commit -m “Added sample HTML file that contain basic syntax”

![Image](https://user-images.githubusercontent.com/107389856/173523002-618b4b71-cdd0-4c99-a4b7-fd28e6d7c355.png)

‘push’: Để làm điều đó, chúng ta phải ‘đẩy’ các tệp của mình lên Remote. Remote là một bản sao trùng lặp của kho lưu trữ ở một nơi khác trên máy chủ từ xa. Để làm điều này, chúng ta phải biết tên của Remote (Chủ yếu là từ xa được đặt tên gốc). Để tìm ra tên đó, gõ lệnh sau.

    - git remote

Như người dùng có thể thấy trong hình trên, nó nói rằng tên từ là origin. Bây giờ chúng ta có thể ‘đẩy’ công việc của mình một cách an toàn bằng lệnh sau.

    - git push origin master

Bây giờ, nếu chúng ta truy cập kho lưu trữ của mình trên trang web GitHub, chúng ta có thể thấy tệp sample.html mà chúng ta đã đẩy đến từ xa – GitHub!

![Image](https://user-images.githubusercontent.com/107382675/173312470-1204e5b4-324c-4c3c-9177-e0bb07166734.png)

*LƯU Ý : Đôi khi, khi người dùng đang sử dụng các lệnh Git trong terminal, nó có thể dẫn người dùng đến trình soạn thảo văn bản VIM (trình soạn thảo văn bản dựa trên CLI). Vì vậy, để thoát khỏi nó, người dùng phải gõ

    - :q

và ENTER.

Mô tả cách pull và push làm việc:

![Image](https://user-images.githubusercontent.com/107382675/173314720-36352134-acfd-4d8d-bb88-a9086a1a4474.png)

Pull là hành động nhận từ GitHub.

Push là hành động gửi đến GitHub.

2. Cách thứ 2: Làm việc trên dự án của người dùng cục bộ sau đó tạo kho lưu trữ trên github và đẩy nó vào remote.

Loại 2 cho phép người dùng tạo một kho lưu trữ mới từ một thư mục hiện có trên máy tính và gửi nó đến GitHub. Trong rất nhiều trường hợp, người dùng có thể đã thực sự tạo ra một cái gì đó trên máy tính mà người dùng muốn đột nhiên biến thành một kho lưu trữ trên GitHub.

khi thực hiện bất kỳ lệnh Git nào, chúng ta phải đảm bảo rằng chúng ta đang ở đúng thư mục trong terminal.

Theo mặc định, bất kỳ thư mục nào trên máy tính không phải là kho lưu trữ Git – nhưng chúng ta có thể biến nó thành kho lưu trữ Git bằng cách thực hiện lệnh sau trong terminal.

    - git init

![Image](https://user-images.githubusercontent.com/107389856/173523170-b961588b-30c8-4489-9315-2d4386f522f6.png)

Sau khi chuyển đổi thư mục của chúng ta sang kho lưu trữ Git, điều đầu tiên chúng ta cần làm là kiểm tra các tệp chúng ta có bằng cách sử dụng lệnh sau.

    - git status

![Image](https://user-images.githubusercontent.com/107389856/173522836-8503e5e4-ba38-4f27-902a-0bf982c40b22.png)

Vì vậy, có hai tập tin trong thư mục đó mà chúng ta cần để thêm vào Repo của chúng ta.

    - git add [FILENAME] [FILENAME] […]

*LƯU Ý: Để thêm vào tất cả các tệp trong Kho lưu trữ của chúng ta, chúng ta có thể sử dụng lệnh sau:

    - git add .

Sau khi khu vực tổ chức (quá trình thêm) hoàn tất, chúng ta có thể kiểm tra xem các tệp có được thêm thành công hay không bằng cách thực hiện git status

Nếu những tệp cụ thể đó có màu xanh lục như hình dưới đây, người dùng đã hoàn thành công việc của mình!

![Image](https://user-images.githubusercontent.com/107389856/173523453-865e14b2-6dce-4d38-a259-59e005960ddb.png)

Sau đó, chúng ta phải commit với một mô tả trong đó.

    - git commit -m “Adding web Survey form”

Nếu kho lưu trữ của người dùng bắt đầu trên GitHub và người dùng đã đưa nó xuống máy tính của mình, một Remote đã được gắn vào nó (Loại 1). Nhưng nếu người dùng đang khởi động kho lưu trữ của mình trên máy tính thì nó không có Remote, vì vậy người dùng cần thêm Remote đó (Loại 2).

Vì vậy, để thêm Remote, chúng ta phải vào GitHub trước. Tạo một kho lưu trữ mới và đặt tên cho nó bất cứ điều gì người dùng muốn lưu trữ trong GitHub. Sau đó nhấp vào nút Tạo kho lưu trữ.

*LƯU Ý: Trong Loại 2, Vui lòng không khởi tạo kho lưu trữ với tệp README khi tạo kho lưu trữ mới trên trang web GitHub.

![Image](https://user-images.githubusercontent.com/107382675/173312279-72bcd828-7ad6-4e1d-a339-b8bf801a04d0.png)

Sau khi nhấp vào nút Tạo kho lưu trữ, người dùng sẽ tìm thấy dạng trang web.

![Image](https://user-images.githubusercontent.com/107382675/173313680-0926ac3f-ab44-43cd-a21c-83769318aefb.png)

Sao chép địa chỉ HTTPS. Bây giờ chúng ta sẽ tạo Remote cho kho lưu trữ của mình.

    - git remote add origin [HTTPS ADDRESS]

Sau khi thực hiện lệnh này, chúng ta có thể kiểm tra xem chúng ta đã thêm thành công Remote hay chưa bằng lệnh sau

    - git remote

Và nếu nó xuất ra Origin thì người dùng đã thêm Remote vào dự án của mình.

*LƯU Ý: Chỉ cần nhớ rằng chúng ta có thể nêu bất kỳ tên nào cho Remote bằng cách thay đổi tên xuất xứ. Ví dụ:

    - git remote add [REMOTE NAME] [HTTPS ADDRESS]

Bây giờ, chúng ta có thể đẩy dự án của mình lên GitHub mà không gặp vấn đề gì!

    - git push origin master

Sau khi hoàn thành từng bước một, nếu người dùng truy cập GitHub, người dùng có thể tìm thấy kho lưu trữ của mình với các tệp!

![Image](https://user-images.githubusercontent.com/107382675/173312470-1204e5b4-324c-4c3c-9177-e0bb07166734.png)