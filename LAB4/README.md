Họ và tên sinh viên: Nguyễn Thành Việt
Mã số sinh viên: 1150080163
Tên bài Lab: Khảo sát và đánh giá bề mặt mạng bằng Nmap

Nội dung đã thực hiện:
Trong bài Lab, tiến hành xây dựng môi trường thực hành gồm máy Windows, máy ảo Kali Linux và Metasploitable 2 trong mạng Host-Only. Kali Linux được sử dụng làm máy quét, Metasploitable 2 làm máy đích phục vụ thực hành. Tiến hành kiểm tra và cài đặt Nmap, xác định địa chỉ IP thực tế của từng máy, kiểm tra kết nối giữa các máy và thực hiện host discovery để phát hiện các host đang hoạt động trong dải mạng nội bộ.

Tiếp theo, thực hiện khảo sát các cổng TCP bằng các kỹ thuật TCP Connect scan (-sT), SYN scan (-sS), FIN scan (-sF), Xmas scan (-sX), NULL scan (-sN) và ACK scan (-sA), sau đó so sánh trạng thái open, closed, filtered và open|filtered. Thực hiện quét UDP có kiểm soát trên các cổng phổ biến; sử dụng -sV để nhận diện dịch vụ và phiên bản, -O để nhận diện hệ điều hành và -A để thu thập tổng hợp thông tin. Ngoài ra, sử dụng NSE script smb-os-discovery để thu thập thông tin SMB và smb-vuln-ms17-010 để kiểm tra dấu hiệu liên quan đến lỗ hổng MS17-010 trên máy ảo thuộc môi trường Lab. Kết quả quét được xuất ra các định dạng normal text, XML và grepable để lưu bằng chứng. Cuối bài thực hiện tình huống before/after hardening bằng cách thay đổi một cấu hình phòng thủ hợp pháp trên máy ảo và quét lại để so sánh sự thay đổi của cổng và dịch vụ.

Kết quả thực hiện:
Đã xây dựng được môi trường mạng Host-Only và xác định được địa chỉ IP của Kali Linux, Metasploitable 2 và các máy tham gia thực hành. Nmap phát hiện được các host đang hoạt động và cho phép khảo sát trạng thái các cổng TCP/UDP trên máy đích. Qua việc so sánh các kỹ thuật -sT, -sS, FIN, Xmas, NULL và ACK scan, có thể quan sát được sự khác nhau trong cách Nmap xác định trạng thái cổng cũng như ảnh hưởng của TCP/IP stack và cơ chế lọc của firewall.

Thông qua -sV, -O và -A, đã thu thập được thông tin về dịch vụ, phiên bản dịch vụ và thông tin hệ điều hành mà Nmap suy đoán. Các NSE script hỗ trợ thu thập thông tin SMB và kiểm tra dấu hiệu MS17-010 dựa trên chính output của công cụ, không thực hiện khai thác lỗ hổng. Kết quả quét được lưu thành các tệp phục vụ đối chiếu và làm bằng chứng. Qua phần before/after hardening, có thể so sánh sự thay đổi của trạng thái cổng và dịch vụ sau khi áp dụng biện pháp phòng thủ. Qua bài thực hành đã hiểu rõ hơn quy trình phát hiện host → khảo sát cổng → nhận diện dịch vụ/hệ điều hành → kiểm tra thông tin bằng NSE → lưu bằng chứng → hardening → quét lại và đánh giá kết quả.
