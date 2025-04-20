# Quản lý chi phí với AWS Budget

## AWS Budget

* là một dịch vụ cung cấp khả năng thiết lập ngân sách để gửi cảnh báo cho bạn khi chi phí vượt quá chi phí mà ngân sách cho phép (hoặc được dự báo sẽ vượt quá ngân sách).

* AWS Budget bao gồm 4 loại budget:

  * Cost Budget
  * Usage Budget
  * RI Budget
  * Savings Plans Budget

## Cost Budget

* Cho phép bạn gửi cảnh báo khi tổng chi phí vượt qua ngưỡng chi phí trong ngân sách.

## Usage Budget

* Cho phép bạn gửi cảnh báo khi tổng mức sử dụng theo từng dịch vụ bạn lựa chọn vượt qua ngưỡng mức sử dụng trong ngân sách.

```example
VD: Mức sử dụng theo số giờ chạy của dịch vụ EC2.
```

## Reservation Instance (RI) Budget

* Cho phép bạn gửi cảnh báo dựa trên mức sử dụng các dịch vụ trả trước (reserve instance) của bạn.

```note
Reserve instance là một phương pháp giảm chi phí sử dụng instance bằng cách cho phép bạn trả trước hoặc cam kết mức sử dụng của instance theo thời hạn 1 - 3 năm.
```

## Savings Plans Budget

* Cho phép bạn gửi cảnh báo dựa trên mức sử dụng các dịch vụ đã được quy định ở trong savings plans.

```note
Savings plans cũng là một phương pháp giảm chi phí sử dụng instance bằng cách cho phép bạn trả trước hoặc cam kết dài hạn (từ 01 đến 03 năm) mức sử dụng của instance đó. Savings plans là mô hình gia ra đời sau và linh hoạt hơn Reserve Instance với mức giảm giá tương đương. Với EC2 Instance, bạn được khuyến khích sử dụng Savings plans.
```

Note: Sử dụng Savings Plans thay vì Reserved Instances cho EC2 sẽ mang lại sự linh hoạt cao hơn với cùng mức giảm giá.

# Nội dung

1. Tạo Cost Budget
2. Tạo Usage Budget
3. Tạo RI Budget
4. Tạo Savings Plans Budget
5. Dọn Dẹp Tài Nguyên

# Lợi ích của việc sử dụng AWS Budget

* Việc sử dụng AWS Budget mang lại nhiều lợi ích cho doanh nghiệp:

  * Kiểm soát chi phí: Giúp bạn theo dõi và kiểm soát chi phí AWS một cách chủ động.
  * Cảnh báo kịp thời: Nhận thông báo ngay khi chi phí vượt quá ngưỡng đã thiết lập.
  * Lập kế hoạch tài chính: Hỗ trợ việc lập kế hoạch tài chính và dự báo chi phí trong tương lai.
  * Tối ưu hóa tài nguyên: Xác định các dịch vụ có chi phí cao để có thể tối ưu hóa việc sử dụng.
  * Phân bổ chi phí: Dễ dàng phân bổ chi phí cho các dự án, phòng ban hoặc khách hàng khác nhau.

# Các bước thiết lập AWS Budget hiệu quả

1. Xác định mục tiêu ngân sách: Hiểu rõ nhu cầu và giới hạn chi tiêu của bạn.

2. Phân tích chi phí hiện tại: Xem xét chi phí hiện tại để thiết lập ngân sách hợp lý.

3. Thiết lập ngưỡng cảnh báo: Đặt ngưỡng cảnh báo ở mức phù hợp (thường là 80% và 100% ngân sách).

4. Cấu hình thông báo: Đảm bảo thông báo được gửi đến đúng người có thẩm quyền.

5. Theo dõi và điều chỉnh: Thường xuyên xem xét và điều chỉnh ngân sách khi cần thiết.
