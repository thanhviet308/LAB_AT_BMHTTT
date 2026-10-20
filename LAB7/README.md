Họ và tên sinh viên: Nguyễn Thành Việt  
Mã số sinh viên: 1150080163  
Tên bài Lab: Xây dựng chính sách Web Protection trên mô hình pfSense + Web Proxy (LAB 7)

**Nội dung thực hiện:**  
Trong bài Lab 7, sử dụng mô hình mạng trên VMware Workstation 17 kế thừa từ LAB 6, gồm pfSense với các vùng WAN, MGMT, LAN và DMZ; máy Windows Server DC01 chạy AD/DNS, hai máy Client-A và Client-B, cùng máy DMZ-WEB. Địa chỉ tương ứng gồm pfSense LAN 10.6.0.1, DC01 10.6.0.10, Client-A 10.6.0.21, Client-B 10.6.0.22 và DMZ-WEB 172.16.6.10. Tạo thêm máy Ubuntu Server 24.04 LTS tên WEB-PROXY, IP 10.6.0.30/24, gateway 10.6.0.1 và DNS 10.6.0.10.

Trên WEB-PROXY, cài Squid, E2Guardian và ClamAV. Thiết kế luồng truy cập từ trình duyệt Client-A/B đến E2Guardian tại cổng 8080, sau đó chuyển qua Squid tại 127.0.0.1:3128. Trên DMZ-WEB, dựng các website mô phỏng bằng Nginx với tên miền *.lab7.test; trên DC01 tạo bản ghi DNS trỏ các tên miền này về 172.16.6.10. Cấu hình trình duyệt của hai client dùng proxy 10.6.0.30:8080. Trên pfSense tạo Alias LAB7_CLIENTS, LAB7_PROXY, WEB_PORTS và MAIL_PORTS, sau đó xây dựng firewall rules cho phép kết nối đến proxy, chặn client truy cập trực tiếp TCP/80 và TCP/443 để ngăn bỏ qua bộ lọc.

Các chính sách Web Protection cần xây dựng gồm: hard block với các website mô phỏng China, Middle East, Job Search và một game cụ thể; warning và temporary bypass cho Weapons, Politics, Religion, Streaming; whitelist cho Normal, Education và Download; giới hạn Entertainment/Game bằng khung giờ 60 phút; quét file tải xuống bằng ClamAV và kiểm tra giới hạn file 100 MB nếu bản Squid hỗ trợ. Phần HTTPS inspection sử dụng CA riêng chỉ là nội dung mở rộng trong môi trường lab cô lập.

**Kết quả thực hiện:**  
[Điền kết quả thực tế sau khi kiểm thử.] Theo yêu cầu bài Lab, Client-A và Client-B phải truy cập được normal.lab7.test khi bật proxy nhưng không được truy cập web trực tiếp khi tắt proxy. Các website thuộc danh sách hard block phải bị chặn; nhóm warning có thể xác nhận để truy cập tạm thời; education.lab7.test được phép truy cập. Chính sách Entertainment/Game cần được đối chiếu trong và ngoài khung giờ, còn chức năng quét EICAR và giới hạn kích thước file phải được xác minh bằng kết quả tải thử và log. Sau mỗi kịch bản, đối chiếu Firewall Log của pfSense, E2Guardian access.log và Squid access.log để xác nhận đường đi của lưu lượng và nguyên nhân cho phép hoặc chặn. Không ghi các kết quả dự kiến thành kết quả đã thực hiện nếu chưa có minh chứng.
