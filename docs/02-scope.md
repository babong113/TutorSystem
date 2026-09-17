# PROJECT SCOPE

## 1. Mục đích

Tài liệu này xác định phạm vi phát triển phiên bản đầu tiên của
Tutor Management System.

Mục đích của tài liệu là xác định rõ:

- Những chức năng được phát triển trong phiên bản MVP.
- Những chức năng chưa thuộc phạm vi của phiên bản hiện tại.
- Các actor tham gia hệ thống.
- Các module chính của hệ thống.
- Mức độ ưu tiên của từng chức năng.
- Tiêu chí để xác định MVP đã hoàn thành.

Sau khi phạm vi MVP được thống nhất, các chức năng phát sinh mới
sẽ được xem xét cho các phiên bản sau thay vì tự động bổ sung vào MVP.

## 2. Mục tiêu MVP

MVP của Tutor Management System phải cung cấp được đầy đủ luồng nghiệp vụ
quản lý lớp học cơ bản của một gia sư.

Luồng chính bao gồm:

Gia sư
→ tạo lớp
→ thiết lập lịch học
→ thêm học sinh hoặc duyệt yêu cầu tham gia lớp
→ tổ chức buổi học
→ điểm danh
→ quản lý yêu cầu nghỉ học hoặc thay đổi lịch
→ thống kê số buổi học
→ tính học phí cuối tháng
→ gửi thông báo đến học sinh.

Học sinh phải có khả năng:

- Tham gia lớp.
- Xem lịch học.
- Xem thông báo.
- Gửi yêu cầu xin nghỉ học.
- Gửi yêu cầu thay đổi lịch học.
- Theo dõi trạng thái các yêu cầu.
- Xem thông tin học phí.

## 3. Actors

| Mã  | Actor   | Mô tả                                                            |
| --- | ------- | ---------------------------------------------------------------- |
| A1  | Tutor   | Gia sư quản lý lớp học, học sinh, lịch học, điểm danh và học phí |
| A2  | Student | Học sinh tham gia lớp và theo dõi thông tin học tập              |
| A3  | Admin   | Quản trị viên quản lý tài khoản và hoạt động chung của hệ thống  |

Trong phiên bản MVP, phụ huynh chưa bắt buộc phải có tài khoản riêng.
Thông tin phụ huynh có thể được lưu trong hồ sơ học sinh để phục vụ
việc gửi thông báo hoặc học phí.

## 4. In Scope

### M01 - Authentication & Authorization

Hệ thống hỗ trợ xác thực và phân quyền người dùng.

Bao gồm:

- Đăng ký tài khoản.
- Đăng nhập.
- Đăng xuất.
- Xác thực bằng JWT.
- Refresh Token.
- Quên mật khẩu.
- Đặt lại mật khẩu.
- Đổi mật khẩu.
- Phân quyền Tutor, Student và Admin.
- Khóa hoặc mở khóa tài khoản.

Business Rules:

- Mỗi tài khoản phải có ít nhất một quyền hợp lệ.
- Người dùng chỉ được truy cập các chức năng thuộc quyền của mình.
- Tài khoản bị khóa không được phép đăng nhập.

### M02 - User Profile

Cho phép người dùng quản lý thông tin cá nhân.

Bao gồm:

- Xem hồ sơ cá nhân.
- Cập nhật họ tên.
- Cập nhật số điện thoại.
- Cập nhật email.
- Cập nhật ảnh đại diện.
- Cập nhật thông tin cơ bản.

### M03 - Student Management

Gia sư có thể quản lý danh sách học sinh của mình.

Bao gồm:

- Xem danh sách học sinh.
- Xem chi tiết học sinh.
- Thêm học sinh mới.
- Cập nhật thông tin học sinh.
- Thêm thông tin phụ huynh.
- Tìm kiếm học sinh.
- Xem các lớp học sinh đang tham gia.
- Xem lịch sử học tập cơ bản.

Trong trường hợp học sinh chưa có tài khoản,
gia sư có thể tạo học sinh và yêu cầu hệ thống tạo tài khoản cho học sinh.

Hệ thống có thể cấp mật khẩu tạm thời để học sinh đăng nhập lần đầu.

### M04 - Class Management

Gia sư có thể tạo và quản lý các lớp học.

Bao gồm:

- Tạo lớp.
- Cập nhật thông tin lớp.
- Xem danh sách lớp.
- Xem chi tiết lớp.
- Đóng hoặc ngừng hoạt động lớp.
- Quản lý danh sách học sinh trong lớp.

Thông tin lớp có thể bao gồm:

- Tên lớp.
- Môn học.
- Mô tả.
- Mức học phí.
- Hình thức tính học phí.
- Trạng thái lớp.

### M05 - Class Membership & Join Request

Hệ thống hỗ trợ hai cách để học sinh tham gia lớp.

#### Cách 1 - Student gửi yêu cầu tham gia

Student có thể:

- Nhập mã lớp hoặc truy cập thông tin lớp.
- Gửi yêu cầu tham gia lớp.
- Xem trạng thái yêu cầu.

Tutor có thể:

- Xem danh sách yêu cầu.
- Chấp nhận yêu cầu.
- Từ chối yêu cầu.

Trạng thái yêu cầu:

- PENDING
- APPROVED
- REJECTED

#### Cách 2 - Tutor trực tiếp thêm Student

Tutor có thể:

- Chọn học sinh có sẵn.
- Thêm học sinh vào lớp.
- Tạo học sinh mới nếu chưa tồn tại.
- Yêu cầu hệ thống tạo tài khoản cho học sinh mới.

Business Rules:

- Một học sinh không được trở thành thành viên trùng lặp trong cùng một lớp.
- Chỉ Tutor sở hữu hoặc quản lý lớp mới được duyệt yêu cầu tham gia.

### M06 - Schedule Management

Gia sư có thể thiết lập lịch học định kỳ cho lớp.

Bao gồm:

- Tạo lịch học.
- Cập nhật lịch học.
- Xóa lịch học.
- Xem lịch học của lớp.
- Thiết lập ngày học trong tuần.
- Thiết lập giờ bắt đầu.
- Thiết lập giờ kết thúc.

Ví dụ:

Lớp Toán 12A

- Thứ 2: 18:00 - 20:00
- Thứ 5: 18:00 - 20:00

Student có thể xem lịch của các lớp mình đang tham gia.

### M07 - Lesson / Session Management

Hệ thống quản lý các buổi học thực tế.

Một lịch học định kỳ có thể tạo ra nhiều buổi học.

Ví dụ:

Lịch định kỳ:

- Thứ 2
- 18:00 - 20:00

Các buổi học thực tế:

- 07/09/2026
- 14/09/2026
- 21/09/2026
- 28/09/2026

Tutor có thể:

- Xem danh sách buổi học.
- Tạo buổi học bổ sung.
- Cập nhật buổi học.
- Hủy buổi học.
- Đánh dấu buổi học đã hoàn thành.

Student có thể:

- Xem các buổi học sắp tới.
- Xem lịch sử các buổi học.

### M08 - Attendance Management

Tutor có thể điểm danh học sinh trong từng buổi học.

Trạng thái điểm danh có thể gồm:

- PRESENT
- ABSENT
- EXCUSED

Tutor có thể:

- Xem danh sách học sinh của buổi học.
- Cập nhật trạng thái điểm danh.
- Ghi chú điểm danh.

Student có thể:

- Xem lịch sử điểm danh của mình.

Dữ liệu điểm danh là một trong các dữ liệu đầu vào
để thống kê số buổi học và tính học phí.

### M09 - Leave Request

Student có thể gửi yêu cầu xin nghỉ một buổi học cụ thể.

Student có thể:

- Chọn buổi học.
- Nhập lý do xin nghỉ.
- Gửi yêu cầu.
- Xem trạng thái yêu cầu.

Tutor có thể:

- Xem yêu cầu xin nghỉ.
- Chấp nhận yêu cầu.
- Từ chối yêu cầu.

Trạng thái:

- PENDING
- APPROVED
- REJECTED

Nếu yêu cầu được duyệt, hệ thống lưu lại thông tin
để phục vụ điểm danh và tính học phí.

### M10 - Schedule Change Request

Hệ thống hỗ trợ hai loại yêu cầu thay đổi lịch.

#### M10.1 - Reschedule Session

Student có thể yêu cầu thay đổi thời gian của một buổi học cụ thể.

Bao gồm:

- Chọn buổi học.
- Đề xuất ngày hoặc giờ mới.
- Nhập lý do.
- Gửi yêu cầu.
- Theo dõi trạng thái.

Tutor có thể:

- Xem yêu cầu.
- Chấp nhận.
- Từ chối.

#### M10.2 - Change Regular Schedule

Student có thể gửi yêu cầu thay đổi lịch học cố định.

Ví dụ:

Lịch hiện tại:

- Thứ 2 và Thứ 5
- 18:00 - 20:00

Lịch mong muốn:

- Thứ 3 và Thứ 6
- 18:00 - 20:00

Tutor có thể xem xét và:

- Chấp nhận yêu cầu.
- Từ chối yêu cầu.
- Thay đổi lịch lớp.
- Hoặc chuyển học sinh sang một lớp phù hợp hơn.

Business Rules:

- Việc một học sinh yêu cầu đổi lịch không đồng nghĩa
  toàn bộ lớp sẽ tự động bị đổi lịch.
- Tutor là người quyết định phương án xử lý cuối cùng.

### M11 - Tuition Management

Hệ thống hỗ trợ tính và quản lý học phí của từng học sinh.

Tutor có thể:

- Xem số buổi học của học sinh trong tháng.
- Xem các buổi được tính học phí.
- Xem tổng tiền học.
- Điều chỉnh học phí nếu cần.
- Xem trạng thái thanh toán.
- Đánh dấu học phí đã thanh toán.

Student có thể:

- Xem học phí của mình theo tháng.
- Xem chi tiết số buổi học.
- Xem trạng thái thanh toán.

Trạng thái học phí MVP:

- UNPAID
- PAID

Ví dụ:

Học sinh: Nguyễn Văn A
Tháng: 09/2026

Số buổi tính phí: 8
Học phí mỗi buổi: 150.000 VND

Tổng học phí:

8 × 150.000 = 1.200.000 VND

Business Rules:

- Học phí được tính dựa trên chính sách của lớp.
- Dữ liệu buổi học và điểm danh có thể ảnh hưởng đến số buổi tính phí.
- Tutor có quyền điều chỉnh học phí trước khi xác nhận.

### M12 - Notification Management

Tutor có thể gửi thông báo đến học sinh.

Bao gồm:

- Tạo thông báo.
- Gửi thông báo cho toàn bộ lớp.
- Gửi thông báo cho một học sinh.
- Xem lịch sử thông báo.

Student có thể:

- Xem danh sách thông báo.
- Xem chi tiết thông báo.
- Đánh dấu đã đọc.

Các sự kiện có thể sinh notification:

- Có thông báo mới từ Tutor.
- Yêu cầu tham gia lớp được duyệt.
- Yêu cầu tham gia lớp bị từ chối.
- Yêu cầu nghỉ học được duyệt.
- Yêu cầu nghỉ học bị từ chối.
- Yêu cầu đổi lịch được xử lý.
- Lịch học thay đổi.
- Có thông tin học phí mới.

MVP chỉ bắt buộc hỗ trợ In-App Notification.

Email, SMS hoặc Push Notification có thể được bổ sung sau.

### M13 - Parent Information

Gia sư có thể lưu thông tin phụ huynh của học sinh.

Thông tin có thể bao gồm:

- Họ tên phụ huynh.
- Số điện thoại.
- Email.
- Quan hệ với học sinh.

Trong MVP:

- Parent chưa cần tài khoản đăng nhập riêng.
- Thông tin phụ huynh được sử dụng để lưu trữ liên hệ.
- Có thể mở rộng để gửi thông báo học phí hoặc lịch học qua email.

### M14 - Dashboard & Statistics

Tutor có thể xem thống kê tổng quan.

Bao gồm:

- Tổng số lớp.
- Tổng số học sinh.
- Số buổi học trong tháng.
- Số học sinh nghỉ học.
- Tổng học phí dự kiến.
- Tổng học phí đã thu.
- Tổng học phí chưa thu.

Student có thể xem:

- Số lớp đang tham gia.
- Số buổi học trong tháng.
- Số buổi nghỉ.
- Học phí hiện tại.

### M15 - Administration

Admin quản lý hoạt động chung của hệ thống.

Bao gồm:

- Xem danh sách tài khoản.
- Xem thông tin tài khoản.
- Khóa tài khoản.
- Mở khóa tài khoản.
- Quản lý quyền.
- Theo dõi dữ liệu hệ thống cơ bản.

## 5. Scope Summary

| Module | Tên module                      | MVP |
| ------ | ------------------------------- | --- |
| M01    | Authentication & Authorization  | Yes |
| M02    | User Profile                    | Yes |
| M03    | Student Management              | Yes |
| M04    | Class Management                | Yes |
| M05    | Class Membership & Join Request | Yes |
| M06    | Schedule Management             | Yes |
| M07    | Lesson / Session Management     | Yes |
| M08    | Attendance Management           | Yes |
| M09    | Leave Request                   | Yes |
| M10    | Schedule Change Request         | Yes |
| M11    | Tuition Management              | Yes |
| M12    | Notification Management         | Yes |
| M13    | Parent Information              | Yes |
| M14    | Dashboard & Statistics          | Yes |
| M15    | Administration                  | Yes |

## 6. Out of Scope

Các chức năng sau chưa thuộc phạm vi MVP:

- Chat realtime giữa Tutor và Student.
- Video call trực tiếp.
- Livestream.
- Mobile Application native.
- Thanh toán học phí trực tuyến.
- Ví điện tử.
- Tích hợp ngân hàng.
- Parent Account riêng.
- SMS Notification.
- Push Notification nâng cao.
- AI chấm bài.
- AI tạo bài tập.
- AI tạo giáo trình.
- Hệ thống thi online.
- LMS hoàn chỉnh.
- Quản lý nhiều chi nhánh trung tâm.
- Marketplace tìm kiếm gia sư.

## 7. Future Scope

Các chức năng có thể phát triển trong các phiên bản sau:

- Tài khoản Parent.
- Parent Dashboard.
- Parent xem lịch học của con.
- Parent xem học phí.
- Gửi học phí qua email.
- Push Notification.
- Chat realtime.
- Thanh toán online.
- QR Code thanh toán học phí.
- AI hỗ trợ tạo bài tập.
- AI hỗ trợ đánh giá tiến độ học tập.
- Báo cáo học tập tự động.
- Xuất hóa đơn PDF.
- Xuất thống kê Excel.
- Mobile Application.

## 8. Priority

| Module                         | Priority |
| ------------------------------ | -------- |
| Authentication & Authorization | MUST     |
| User Profile                   | MUST     |
| Student Management             | MUST     |
| Class Management               | MUST     |
| Class Membership               | MUST     |
| Schedule Management            | MUST     |
| Lesson Management              | MUST     |
| Attendance Management          | MUST     |
| Leave Request                  | MUST     |
| Schedule Change Request        | MUST     |
| Tuition Management             | MUST     |
| Notification                   | MUST     |
| Parent Information             | SHOULD   |
| Dashboard & Statistics         | SHOULD   |
| Administration                 | MUST     |

Giải thích mức độ ưu tiên:

- MUST: bắt buộc phải hoàn thành để hệ thống hoạt động đúng nghiệp vụ.
- SHOULD: rất nên có nhưng có thể giản lược nếu thiếu thời gian.
- COULD: chỉ thực hiện nếu còn đủ thời gian.
- WON'T: không thực hiện trong MVP hiện tại.

## 9. MVP Definition of Done

MVP được xem là hoàn thành khi hệ thống thực hiện thành công
các luồng nghiệp vụ chính sau.

### Luồng 1 - Tạo và quản lý lớp

Tutor
→ đăng nhập
→ tạo lớp
→ thiết lập lịch học
→ thêm học sinh
→ xem danh sách học sinh.

### Luồng 2 - Học sinh tham gia lớp

Student
→ đăng nhập
→ gửi yêu cầu tham gia lớp
→ Tutor nhận yêu cầu
→ Tutor chấp nhận
→ Student trở thành thành viên lớp.

### Luồng 3 - Tutor chủ động thêm học sinh

Tutor
→ tạo hoặc tìm Student
→ thêm Student vào lớp
→ nếu Student chưa có account
→ hệ thống tạo account
→ Student đăng nhập.

### Luồng 4 - Quản lý buổi học

Schedule
→ tạo Lesson
→ Tutor thực hiện buổi học
→ điểm danh Student
→ Lesson hoàn thành.

### Luồng 5 - Xin nghỉ học

Student
→ chọn Lesson
→ gửi Leave Request
→ Tutor xem yêu cầu
→ APPROVE / REJECT
→ Student xem kết quả.

### Luồng 6 - Yêu cầu đổi lịch

Student
→ chọn Lesson hoặc Class
→ đề xuất lịch mới
→ gửi yêu cầu
→ Tutor xem xét
→ APPROVE / REJECT
→ Student nhận kết quả.

### Luồng 7 - Học phí cuối tháng

Lesson
→ Attendance
→ thống kê số buổi
→ tính học phí
→ Tutor kiểm tra
→ xác nhận học phí
→ Student xem học phí
→ Tutor cập nhật PAID / UNPAID.

### Luồng 8 - Thông báo

Tutor
→ tạo thông báo
→ chọn lớp hoặc Student
→ gửi thông báo
→ Student đăng nhập
→ xem thông báo.

Ngoài ra hệ thống phải đảm bảo:

- Tutor chỉ quản lý được các lớp thuộc phạm vi của mình.
- Student chỉ xem được dữ liệu liên quan đến bản thân.
- Admin có quyền quản trị toàn hệ thống.
- JWT được sử dụng để xác thực API.
- Authorization được kiểm tra ở backend.
- Dữ liệu được lưu trữ bằng PostgreSQL.
- Không để học sinh tham gia trùng một lớp.
- Không để một yêu cầu được xử lý nhiều lần.
- Các thay đổi quan trọng về lịch học phải được lưu lại.
