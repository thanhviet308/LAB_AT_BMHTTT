Họ và tên sinh viên: Nguyễn Thành Việt
Mã số sinh viên: 1150080163
Tên bài Lab: Xác thực Active Directory và chính sách truy cập trên pfSense (LAB 6)

Nội dung đã thực hiện:
Trong bài Lab, tiến hành xây dựng mô hình pfSense trên VMware Workstation 17 với bốn vùng mạng WAN, MGMT, LAN và DMZ. Mạng quản trị MGMT sử dụng dải 192.168.56.0/24, LAN sử dụng 10.6.0.0/24 và DMZ sử dụng 172.16.6.0/24. Hệ thống gồm pfSense, Domain Controller Windows Server, Client-A, Client-B và Ubuntu Server đóng vai trò DMZ-WEB. Các máy được gán card mạng ảo và cấu hình IP theo sơ đồ LAB 6.

Tiếp theo, cấu hình Active Directory Domain Services và DNS cho domain lab6.test, tạo OU LAB6-Users và các tài khoản sv_a, sv_b, svc_pfsense_ldap. Trên Ubuntu Server, cài Nginx và sử dụng bốn địa chỉ IP mô phỏng GENERAL_SITE, JOB_SITE, SOCIAL_SITE và RESTRICTED_SITE. Trên pfSense, thiết lập LDAP Authentication Server, kiểm tra xác thực tài khoản miền và cấu hình Captive Portal trên LAN. Sau đó tạo các Firewall Alias, Schedule LUNCH_WINDOW và WORK_HOURS, rồi triển khai bảy kịch bản chính sách: chặn JOB_SITE theo Client-A, chặn RESTRICTED_SITE cho hai client, giới hạn SOCIAL_SITE theo giờ nghỉ, giới hạn HTTP/HTTPS theo giờ hành chính, cô lập DMZ khỏi LAN, so sánh Block/Reject và đọc Firewall Log/State Table. Khi thay đổi rule, thực hiện Apply Changes và kiểm tra kết nối mới hoặc Reset States khi cần.

Kết quả thực hiện:
[Dự kiến — thay bằng kết quả thực tế sau khi hoàn thành bài Lab.] Mô hình pfSense phân tách được WAN, MGMT, LAN và DMZ; hai tài khoản sv_a và sv_b xác thực được qua LDAP và Captive Portal. Các rule theo IP, port và schedule tạo ra kết quả Allow/Block tương ứng với từng kịch bản; log và state table hỗ trợ đối chiếu lưu lượng thực tế. Qua bài thực hành, nắm được quy trình cấu hình mạng ảo → triển khai AD/DNS và DMZ-WEB → tích hợp LDAP/Captive Portal → xây dựng Alias/Schedule và firewall rules → kiểm thử và phân tích log.
