Họ và tên sinh viên: Nguyễn Thành Việt
Mã số sinh viên: 1150080163
Tên bài Lab: Thiết lập mô hình tường lửa pfSense

Nội dung đã thực hiện:
Trong bài Lab, tiến hành xây dựng môi trường thực hành tường lửa pfSense gồm máy ảo pfSense, Domain Controller sử dụng Windows Server, máy DMZ-Web sử dụng Windows Server và máy LAN-Test sử dụng Ubuntu Server. pfSense được cấu hình với ba vùng mạng WAN, LAN và DMZ; trong đó LAN sử dụng dải 10.0.0.0/8 và DMZ sử dụng dải 172.16.0.0/16. Các máy được cấu hình địa chỉ IP tĩnh phù hợp để kiểm tra kết nối và quản trị hệ thống.

Tiếp theo, tiến hành cài đặt và cấu hình pfSense, thiết lập địa chỉ cho các interface, truy cập giao diện WebGUI và kiểm tra Outbound NAT. Trên Domain Controller tiến hành cấu hình địa chỉ IP, cài đặt Active Directory Domain Services và DNS, đồng thời cấu hình DNS Forwarder. Máy DMZ-Web được cấu hình trong vùng DMZ và cài đặt IIS để làm Web Server phục vụ kiểm thử. Sau khi hoàn thành mô hình nền tảng, tiến hành chuẩn hóa firewall rules và thực hiện các tình huống gồm chặn ICMP nhưng vẫn cho phép Web/DNS, chỉ cho phép một host cụ thể trong LAN truy cập Internet, cô lập DMZ khỏi LAN, cấu hình Port Forward từ WAN đến Web Server trong DMZ và bật logging để theo dõi Firewall Log. Sau mỗi lần thay đổi rule hoặc NAT, thực hiện Apply Changes và Reset States trước khi kiểm thử lại.

Kết quả thực hiện:
Đã xây dựng được mô hình mạng sử dụng pfSense làm tường lửa phân tách WAN, LAN và DMZ. Máy Domain Controller trong LAN có thể sử dụng pfSense làm gateway, máy DMZ-Web hoạt động trong vùng DMZ và dịch vụ IIS được sử dụng để kiểm tra kết nối Web. Qua quá trình cấu hình firewall rule có thể quan sát được sự thay đổi của lưu lượng khi các rule Allow/Block được áp dụng.

Thông qua các tình huống thực hành, đã kiểm tra được cơ chế chặn ICMP trong khi vẫn cho phép các dịch vụ cần thiết, giới hạn quyền truy cập Internet theo từng host, cô lập lưu lượng từ DMZ vào LAN và sử dụng NAT Port Forward để chuyển tiếp kết nối từ WAN đến Web Server trong DMZ. Firewall Log hỗ trợ theo dõi các kết nối được cho phép hoặc bị chặn. Qua bài thực hành đã hiểu rõ hơn quy trình xây dựng mô hình mạng → cấu hình interface và địa chỉ IP → thiết lập NAT/firewall rule → kiểm thử lưu lượng → đọc log → đánh giá kết quả.
