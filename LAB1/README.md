Họ và tên sinh viên: Nguyễn Thành Việt
Mã số sinh viên: 1150080163
Tên bài Lab: Examining SSH & Telnet in Wireshark

Nội dung đã thực hiện:
Trong bài Lab, tiến hành xây dựng môi trường thực hành trên các máy ảo, cấu hình kết nối mạng giữa các máy, cài đặt và cấu hình dịch vụ Telnet và SSH. Sử dụng máy Client để thực hiện kết nối Telnet và SSH đến Server. Đồng thời sử dụng Wireshark để bắt và phân tích các gói tin TCP port 23 của Telnet và TCP port 22 của SSH. Thực hiện Follow TCP Stream để quan sát dữ liệu truyền qua hai giao thức và so sánh khả năng bảo mật của Telnet với SSH. Ngoài ra, thực hiện tìm hiểu và minh họa phương thức đăng nhập SSH bằng public key.

Kết quả thực hiện:
Đã thiết lập thành công môi trường thực hành và thực hiện kết nối Telnet, SSH giữa Client và Server. Wireshark bắt được các gói tin liên quan đến quá trình kết nối. Qua phân tích cho thấy dữ liệu của phiên Telnet có thể quan sát được dưới dạng có thể đọc khi bắt đúng lưu lượng, trong khi nội dung phiên SSH được mã hóa nên không thể đọc trực tiếp bằng Wireshark. Qua bài thực hành đã thấy được sự khác biệt về mức độ bảo mật giữa Telnet và SSH, hiểu được vai trò của mã hóa, xác thực và SSH public-key authentication trong việc bảo vệ kết nối từ xa.