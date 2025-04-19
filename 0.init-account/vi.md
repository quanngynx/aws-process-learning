# Tổng quan

* Thiết lập MFA (Multi-factor Authentication)
* Tạo Admin Group và Admin User để quản lý tài nguyên AWS thay vì sử dụng root

## Các khái niệm cơ bản

Note: AWS khuyến nghị không sử dụng root user cho các tác vụ hàng ngày. Thay vào đó, hãy tạo IAM User với quyền quản trị phù hợp để giảm thiểu rủi ro bảo mật.

### MFA(Multi-factor Authentication)

MFA là tính năng bảo mật nâng cao cho tài khoản AWS. Khi kích hoạt, bạn sẽ cần nhập mã OTP (One-time Password) mỗi lần đăng nhập vào tài khoản AWS, tạo lớp bảo vệ thứ hai ngoài mật khẩu thông thường.

### IAM Group

IAM Group là công cụ quản lý người dùng của AWS, cho phép gom nhiều IAM User vào một nhóm. Tất cả IAM User trong cùng một nhóm sẽ được thừa hưởng các quyền được gán cho nhóm đó, giúp quản lý quyền dễ dàng hơn.

### IAM User

IAM User là đơn vị người dùng trong AWS. Mỗi IAM User có thông tin đăng nhập riêng và được cấp quyền truy cập cụ thể vào tài nguyên AWS. IAM User được tạo để cấp quyền truy cập dài hạn vào tài khoản AWS.

### AWS Support

là đơn vị cung cấp dịch vụ hỗ trợ khách hàng của AWS, giúp giải quyết các vấn đề kỹ thuật và hỗ trợ xác thực tài khoản.

### AWS Management Console

AWS Management Console là giao diện web cho phép quản lý và tương tác với các dịch vụ AWS một cách trực quan.

## Nội dung chính

### Thiết lập MFA cho tài khoản Root

1. Đăng nhập vào AWS Management Console
2. Truy cập trang quản lý tài khoản

* Nhấp vào tên tài khoản của bạn ở góc phải trên cùng
* Chọn My Security Credentials từ menu thả xuống

3. Thiết lập MFA

* Mở rộng phần Multi-factor authentication (MFA)
* Nhấp vào Activate MFA
* Chọn loại thiết bị MFA:
  * Virtual MFA device: Sử dụng ứng dụng xác thực như Google Authenticator
  * Hardware TOTP token: Sử dụng thiết bị phần cứng chuyên dụng
  * Security key: Sử dụng khóa bảo mật FIDO

4. Cấu hình MFA cho thiết bị ảo (phổ biến nhất)

* Cài đặt ứng dụng xác thực trên điện thoại của bạn (Google * Authenticator, Authy, Microsoft Authenticator, v.v.)
* Nhấp vào Show QR code và quét mã QR bằng ứng dụng xác thực
* Nhập hai mã xác thực liên tiếp từ ứng dụng xác thực
* Nhấp vào Assign MFA

5. Sao lưu thông tin MFA

* Lưu mã QR hoặc khóa bí mật được cung cấp trong quá trình thiết lập
* Lưu trữ an toàn thông tin này để phòng trường hợp mất thiết bị

### Tạo Admin Group và Admin User

1. Truy cập dịch vụ IAM

* Đăng nhập vào AWS Management Console bằng tài khoản root
* Tìm kiếm “IAM” trong thanh tìm kiếm dịch vụ
* Chọn dịch vụ IAM (Identity and Access Management)

2. Tạo Admin Group

* Trong dashboard IAM, nhấp vào User groups ở menu bên trái
* Nhấp vào nút Create group
* Nhập tên cho nhóm (ví dụ: “Administrators”)
* Tìm và chọn policy AdministratorAccess trong danh sách policies
* Nhấp vào Create group để hoàn tất

3. Tạo Admin User

* Trong dashboard IAM, nhấp vào Users ở menu bên trái
* Nhấp vào nút Add users
* Nhập tên người dùng (ví dụ: “AdminUser”)
* Chọn AWS Management Console access trong phần Access type
* Cấu hình mật khẩu:
  * Chọn Custom password và nhập mật khẩu mạnh
  * Bỏ chọn “User must create a new password at next sign-in” nếu bạn không muốn thay đổi mật khẩu ở lần đăng nhập đầu tiên

4. Thêm User vào Admin Group

* Trong trang “Add user to group”, chọn nhóm Administrators đã tạo ở bước * trước
* Nhấp vào Next: Tags
* (Tùy chọn) Thêm tags nếu cần
* Nhấp vào Next: Review
* Xem lại thông tin và nhấp vào Create user

5. Lưu thông tin đăng nhập

* Tải xuống hoặc sao chép thông tin đăng nhập (bao gồm đường dẫn đăng * nhập, tên người dùng và mật khẩu)
* Lưu trữ thông tin này một cách an toàn

6. Thiết lập MFA cho Admin User

* Quay lại danh sách Users trong IAM
* Chọn tên người dùng vừa tạo
* Chọn tab Security credentials
* Trong phần Multi-factor authentication (MFA), nhấp vào Assign MFA device
* Làm theo các bước tương tự như khi thiết lập MFA cho tài khoản root

### Hỗ trợ xác thực tài khoản

#### Các vấn đề phổ biến khi xác thực tài khoản

* Không nhận được email xác nhận
* Thẻ tín dụng không được chấp nhận
* Xác minh danh tính thất bại
* Không thể đăng nhập sau khi đăng ký

#### Liên hệ AWS Support

* Truy cập aws.amazon.com/support
* Nhấp vào Create case
* Chọn loại hỗ trợ Account and billing support
* Điền đầy đủ thông tin về vấn đề của bạn
* Nhấp vào Submit để gửi yêu cầu hỗ trợ

### Khám phá AWS Management Console

#### Tổng quan về AWS Management Console

* Thanh điều hướng phía trên cùng:
  * Menu dịch vụ: Truy cập nhanh đến các dịch vụ AWS
  * Thanh tìm kiếm: Tìm kiếm dịch vụ, tài liệu và tài nguyên
  * Khu vực: Chọn khu vực AWS để làm việc
  * Tài khoản: Quản lý cài đặt tài khoản và đăng xuất
  * Hỗ trợ: Truy cập tài liệu và hỗ trợ

#### Các dịch vụ AWS cơ bản cho người mới bắt đầu

* EC2: Máy chủ ảo
* S3: Lưu trữ đối tượng
* RDS: Cơ sở dữ liệu quan hệ
* Lambda: Tính toán không cần máy chủ
* CloudWatch: Giám sát và nhật ký

#### Cá nhân hóa AWS Management Console

1. Tạo trang chủ tùy chỉnh:

* Nhấp vào Edit ở góc phải trên cùng của trang chủ console
* Thêm, xóa hoặc sắp xếp lại các widget theo nhu cầu
* Nhấp vào Save để lưu thay đổi

2. Tạo bookmark cho các dịch vụ thường dùng:

* Nhấp vào dấu sao bên cạnh tên dịch vụ trong menu dịch vụ
* Các dịch vụ đã đánh dấu sẽ xuất hiện trong phần Recently visited  services

# Tài liệu tham khảo

[awsstudygroup](https://000001.awsstudygroup.com/)

[AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)

[AWS Security Best Practices](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html)

[AWS Support Plans](https://aws.amazon.com/vi/premiumsupport/plans/)

[Getting Started with AWS](https://aws.amazon.com/vi/getting-started/)
