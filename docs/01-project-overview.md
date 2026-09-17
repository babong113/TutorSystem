# PROJECT OVERVIEW

## 1. Tên dự án

Tutor Management System

## 2. Tổng quan dự án

Tutor Management System là hệ thống hỗ trợ gia sư quản lý học sinh,
lớp học, lịch học, buổi học, học phí và các thông báo liên quan
đến quá trình giảng dạy.

Hệ thống tập trung vào việc hỗ trợ gia sư quản lý hoạt động dạy học
một cách tập trung thay vì phải sử dụng nhiều công cụ riêng biệt
như sổ sách, Excel, tin nhắn hoặc các ứng dụng nhắn tin.

Gia sư có thể tạo lớp học, thêm học sinh vào lớp, quản lý lịch học,
theo dõi các buổi học, điểm danh học sinh, xử lý các yêu cầu nghỉ học
hoặc thay đổi lịch học và thống kê học phí theo từng tháng.

Học sinh có thể tham gia lớp bằng cách gửi yêu cầu tham gia lớp
hoặc được gia sư trực tiếp thêm vào lớp và cấp tài khoản sử dụng hệ thống.

Sau khi tham gia lớp, học sinh có thể xem lịch học, các buổi học sắp tới,
thông báo từ gia sư, thông tin học phí và gửi các yêu cầu liên quan
đến việc nghỉ học hoặc thay đổi lịch học.

Quản trị viên chịu trách nhiệm quản lý tài khoản người dùng,
phân quyền và giám sát hoạt động chung của hệ thống.

## 3. Vấn đề cần giải quyết

Trong quá trình giảng dạy, gia sư thường phải quản lý nhiều thông tin
liên quan đến học sinh và lớp học.

Một số vấn đề phổ biến bao gồm:

- Khó quản lý danh sách học sinh của nhiều lớp khác nhau.
- Khó theo dõi lịch học và các buổi học đã diễn ra.
- Gia sư phải quản lý lịch học bằng sổ sách, Excel hoặc tin nhắn.
- Học sinh khó theo dõi lịch học và các thay đổi trong lịch.
- Việc xin nghỉ hoặc xin thay đổi lịch học thường được thực hiện
  qua tin nhắn và khó kiểm soát.
- Khó theo dõi số buổi học thực tế của từng học sinh.
- Khó tính toán học phí cuối tháng.
- Khó theo dõi trạng thái đóng học phí của từng học sinh.
- Khó gửi thông báo đồng thời đến nhiều học sinh trong cùng lớp.
- Phụ huynh có thể không nắm được đầy đủ thông tin về lịch học
  và học phí của học sinh.

Tutor Management System được xây dựng nhằm tập trung các hoạt động
quản lý học sinh, lớp học, lịch học và học phí trên một hệ thống duy nhất.

## 4. Mục tiêu của hệ thống

Hệ thống được xây dựng với các mục tiêu chính:

- Cho phép gia sư quản lý học sinh.
- Cho phép gia sư tạo và quản lý lớp học.
- Cho phép học sinh gửi yêu cầu tham gia lớp.
- Cho phép gia sư chủ động thêm học sinh vào lớp.
- Hỗ trợ tạo tài khoản cho học sinh được gia sư thêm vào hệ thống.
- Quản lý lịch học của từng lớp.
- Quản lý các buổi học thực tế.
- Theo dõi tình trạng tham gia học của học sinh.
- Cho phép học sinh gửi yêu cầu xin nghỉ học.
- Cho phép học sinh gửi yêu cầu thay đổi lịch học.
- Cho phép học sinh gửi yêu cầu thay đổi lịch học cố định.
- Cho phép gia sư duyệt hoặc từ chối các yêu cầu thay đổi lịch.
- Hỗ trợ gia sư gửi thông báo đến học sinh.
- Hỗ trợ học sinh xem lịch học và các thông báo.
- Thống kê số buổi học của từng học sinh theo tháng.
- Tính học phí của từng học sinh vào cuối tháng.
- Theo dõi trạng thái đóng học phí.
- Hỗ trợ gửi thông tin học phí đến học sinh hoặc phụ huynh.
- Hỗ trợ quản trị viên quản lý tài khoản và phân quyền hệ thống.

## 5. Đối tượng sử dụng

Hệ thống có ba nhóm người dùng chính.

### 5.1 Học sinh

Học sinh là người tham gia các lớp học do gia sư quản lý.

Học sinh có thể:

- Đăng ký và đăng nhập.
- Quản lý hồ sơ cá nhân.
- Gửi yêu cầu tham gia lớp.
- Xem các lớp đang tham gia.
- Xem lịch học.
- Xem các buổi học sắp tới.
- Xem thông báo từ gia sư.
- Gửi yêu cầu xin nghỉ học.
- Gửi yêu cầu chuyển lịch của một buổi học.
- Gửi yêu cầu thay đổi lịch học cố định.
- Theo dõi trạng thái các yêu cầu đã gửi.
- Xem thông tin học phí.
- Xem trạng thái đóng học phí.

### 5.2 Gia sư

Gia sư là người quản lý lớp học và học sinh.

Gia sư có thể:

- Tạo và quản lý hồ sơ gia sư.
- Tạo lớp học.
- Cập nhật thông tin lớp học.
- Thêm học sinh vào lớp.
- Cấp tài khoản cho học sinh chưa có tài khoản.
- Xem và duyệt yêu cầu tham gia lớp.
- Quản lý danh sách học sinh.
- Thiết lập lịch học cho lớp.
- Quản lý các buổi học.
- Điểm danh học sinh.
- Xem yêu cầu xin nghỉ học.
- Xem yêu cầu thay đổi lịch học.
- Chấp nhận hoặc từ chối yêu cầu của học sinh.
- Gửi thông báo đến học sinh.
- Theo dõi số buổi học của từng học sinh.
- Thống kê học phí hàng tháng.
- Cập nhật trạng thái đóng học phí.

### 5.3 Quản trị viên

Quản trị viên chịu trách nhiệm quản lý hệ thống.

Quản trị viên có thể:

- Quản lý tài khoản người dùng.
- Quản lý quyền truy cập.
- Khóa hoặc mở khóa tài khoản.
- Quản lý dữ liệu hệ thống.
- Theo dõi hoạt động chung của hệ thống.

## 6. Phạm vi hệ thống

Phiên bản đầu tiên của hệ thống tập trung vào các chức năng cốt lõi:

- Authentication và Authorization.
- Quản lý tài khoản người dùng.
- Quản lý hồ sơ học sinh.
- Quản lý hồ sơ gia sư.
- Quản lý lớp học.
- Quản lý danh sách học sinh trong lớp.
- Quản lý yêu cầu tham gia lớp.
- Quản lý lịch học.
- Quản lý buổi học.
- Quản lý điểm danh.
- Quản lý yêu cầu xin nghỉ học.
- Quản lý yêu cầu thay đổi lịch học.
- Quản lý thông báo.
- Thống kê số buổi học.
- Tính học phí của từng học sinh theo tháng.
- Theo dõi trạng thái đóng học phí.
- Quản trị hệ thống.

## 7. Mô hình hoạt động

Quy trình cơ bản của hệ thống:

1. Gia sư đăng ký và đăng nhập vào hệ thống.

2. Gia sư tạo lớp học.

3. Gia sư thiết lập thông tin lớp và lịch học.

4. Học sinh có thể tham gia lớp theo một trong hai cách:
   - Học sinh gửi yêu cầu tham gia lớp.
   - Gia sư trực tiếp thêm học sinh vào lớp.

5. Nếu học sinh chưa có tài khoản, gia sư có thể tạo tài khoản
   và cấp thông tin đăng nhập cho học sinh.

6. Học sinh đăng nhập vào hệ thống.

7. Học sinh xem lớp đang tham gia và lịch học.

8. Hệ thống tạo các buổi học dựa trên lịch của lớp.

9. Gia sư thực hiện buổi học và điểm danh học sinh.

10. Học sinh có thể xem các thông báo từ gia sư.

11. Cuối tháng, hệ thống thống kê số buổi học của từng học sinh.

12. Hệ thống tính học phí tương ứng của từng học sinh.

13. Gia sư cập nhật trạng thái đóng học phí.

14. Học sinh có thể xem thông tin học phí của mình.

## 8. Luồng yêu cầu nghỉ học và thay đổi lịch học

Ngoài luồng quản lý lớp học thông thường,
hệ thống hỗ trợ học sinh gửi các yêu cầu liên quan đến lịch học.

### 8.1 Yêu cầu xin nghỉ một buổi học

Học sinh có thể chọn một buổi học cụ thể và gửi yêu cầu xin nghỉ.

Luồng xử lý:

Học sinh
→ chọn buổi học
→ gửi yêu cầu xin nghỉ
→ nhập lý do
→ yêu cầu ở trạng thái chờ duyệt
→ gia sư xem yêu cầu
→ gia sư chấp nhận hoặc từ chối.

Nếu được chấp nhận, trạng thái tham gia của học sinh trong buổi học
sẽ được cập nhật phù hợp.

### 8.2 Yêu cầu chuyển lịch của một buổi học

Học sinh có thể gửi yêu cầu thay đổi thời gian của một buổi học cụ thể.

Ví dụ:

Buổi học hiện tại:

20/09/2026
18:00 - 20:00

Học sinh đề xuất:

21/09/2026
19:00 - 21:00

Luồng xử lý:

Học sinh
→ chọn buổi học
→ đề xuất thời gian mới
→ nhập lý do
→ gửi yêu cầu
→ chờ gia sư duyệt
→ gia sư chấp nhận hoặc từ chối.

Việc chấp nhận yêu cầu không bắt buộc phải thay đổi lịch
cho toàn bộ học sinh trong lớp nếu yêu cầu chỉ áp dụng cho một học sinh.

### 8.3 Yêu cầu thay đổi lịch học cố định

Trong trường hợp học sinh không còn phù hợp với lịch học hiện tại,
học sinh có thể gửi yêu cầu thay đổi lịch học lâu dài.

Ví dụ:

Lịch hiện tại:

Thứ 2 và Thứ 5
18:00 - 20:00

Học sinh đề xuất:

Thứ 3 và Thứ 6
18:00 - 20:00

Luồng xử lý:

Học sinh
→ chọn lớp
→ gửi yêu cầu thay đổi lịch học
→ nhập lịch mong muốn
→ nhập lý do
→ chờ gia sư duyệt
→ gia sư xem xét
→ chấp nhận hoặc từ chối.

Nếu được chấp nhận,
gia sư có thể cập nhật lịch học phù hợp hoặc chuyển học sinh
sang một lớp khác có lịch phù hợp hơn.

## 9. Nền tảng hệ thống

Hệ thống được xây dựng dưới dạng Web Application.

### Backend

- Java
- Spring Boot
- Spring Security
- JWT
- Spring Data JPA

### Database

- PostgreSQL

### Frontend

- ReactJS

### Version Control

- Git
- GitHub

## 10. Các giới hạn của phiên bản đầu

Phiên bản đầu tiên chưa tập trung vào các chức năng:

- Video call trực tiếp trên hệ thống.
- Livestream.
- Chat realtime.
- Ví điện tử nội bộ.
- Thanh toán trực tuyến.
- AI chấm bài tự động.
- AI tạo giáo trình.
- Mobile Application.
- Hệ thống học trực tuyến trực tiếp trên website.

## 11. Kết quả mong đợi

Sau khi hoàn thành, hệ thống phải cho phép thực hiện đầy đủ các luồng chính:

Gia sư
→ tạo lớp
→ thiết lập lịch học
→ thêm học sinh
→ quản lý buổi học
→ điểm danh
→ thống kê học phí
→ gửi thông báo.

Học sinh
→ tham gia lớp
→ xem lịch học
→ xem thông báo
→ gửi yêu cầu xin nghỉ hoặc thay đổi lịch
→ theo dõi trạng thái yêu cầu
→ xem học phí.

Cuối mỗi tháng:

Các buổi học
→ dữ liệu điểm danh
→ thống kê số buổi học
→ tính học phí
→ tạo thông tin học phí
→ gửi thông báo đến học sinh hoặc phụ huynh.

Hệ thống phải đảm bảo phân quyền giữa Student, Tutor và Admin
và dữ liệu được lưu trữ tập trung trong PostgreSQL.
