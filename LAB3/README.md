Họ và tên sinh viên: Nguyễn Thành Việt
Mã số sinh viên: 1150080163
Tên bài Lab: Nhận diện và ứng phó các mối đe dọa đến an toàn thông tin

Nội dung đã thực hiện:
Trong bài Lab, tiến hành xây dựng môi trường thực hành trên máy ảo Windows 11 và chuẩn bị các công cụ Microsoft Defender, Sysmon, Autoruns, Process Explorer, Wireshark và Python phục vụ việc quan sát, thu thập bằng chứng và phân tích các mối đe dọa an toàn thông tin. Thực hiện thu thập baseline của hệ thống, xác định tài sản, lỗ hổng, mối đe dọa và rủi ro; đồng thời phân loại các nguồn đe dọa gồm hành động vô ý, hành động cố ý, thảm họa tự nhiên, lỗi kỹ thuật và lỗi quản lý.

Tiến hành kiểm chứng khả năng phát hiện của Microsoft Defender bằng tệp kiểm thử EICAR; tạo tài khoản thử nghiệm để quan sát các sự kiện đăng nhập thành công và thất bại thông qua Windows Event Log. Thực hiện mô phỏng persistence lành tính và sử dụng Sysmon, Autoruns, Process Explorer để nhận diện các dấu vết liên quan. Tạo HTTP server chỉ lắng nghe trên địa chỉ 127.0.0.1 và sử dụng Wireshark để quan sát lưu lượng HTTP, sau đó so sánh với lưu lượng HTTPS/TLS. Ngoài ra, thực hiện tải cục bộ có giới hạn để minh họa DoS, phân tích dataset DDoS và Mail Bombing offline, đồng thời phân tích các mẫu Social Engineering, Phishing và Spear Phishing. Cuối bài tiến hành cleanup, kiểm tra lại trạng thái hệ thống và tính SHA-256 cho các bằng chứng đã thu thập.

Kết quả thực hiện:
Đã xây dựng được môi trường thực hành và thu thập baseline của máy Windows 11. Microsoft Defender nhận diện được tệp kiểm thử EICAR và ghi nhận thông tin phát hiện. Windows Event Log ghi nhận được các sự kiện xác thực của tài khoản thử nghiệm, bao gồm đăng nhập hợp lệ và đăng nhập thất bại. Sysmon, Autoruns và Process Explorer hỗ trợ phát hiện và đối chiếu các artefact persistence cũng như tiến trình đang lắng nghe cổng cục bộ.

Qua phân tích Wireshark, lưu lượng HTTP cục bộ cho phép quan sát dữ liệu huấn luyện ở dạng có thể đọc, trong khi nội dung ứng dụng của kết nối HTTPS/TLS được mã hóa và không thể đọc trực tiếp theo cách tương tự. Bài Lab cũng giúp phân biệt DoS và DDoS, nhận diện dấu hiệu bất thường trong dữ liệu Mail Bombing và các chỉ dấu của Social Engineering/Phishing. Sau khi hoàn thành, các artefact thử nghiệm được loại bỏ, Microsoft Defender vẫn hoạt động và bằng chứng được lưu, kiểm tra bằng SHA-256. Qua bài thực hành đã hiểu rõ hơn mối quan hệ giữa Asset, Vulnerability, Threat, Risk và Attack, cũng như quy trình Baseline → Observe → Detect → Contain → Recover → Verify.
