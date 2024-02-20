# Lý thuyết:
1. Docker, docker-composer là gì?
    - Docker là một nền tảng mã nguồn mở giúp đóng gói ứng dụng và các thuộc tính của chúng vào thứ được gọi là container. Các container này có dung lượng nhẹ và được ảo hoá khi khởi chạy, không phụ thuộc vào phần cứng bên dưới. Docker giúp đơn giản hoá quy trình building, deploying và running cho các lập trình viên
    - Docker compose là một công cụ để định nghĩa và chạy nhiều container đồng thời trong cùng một ứng dụng Docker (multi-container). 
2. Linux vs Unix vs BSD hay *nix? macOS thuộc loại nào?
   -	Unix là một họ các hệ điều hành đa nhiệm, đa người dùng được kế thừa từ hệ điều hành Unix của AT&T phát triển năm 1969
   -	*nix (hay Unix-like) là tập các hệ điều hành với cách hành xử và hoạt động tương tự UNIX nhưng không cần thiết phải được công nhận hay theo tiêu chuẩn của UNIX
   - Linux là một họ các hệ điều hành Unix-like dựa trên nhân Linux
   -	BSD (Berkeley Software Distribution hay Berkeley Standard Distribution) là một hệ điều hành mã nguồn mở được phát triển dựa trên Unix). Ngày nay nó đã dừng hoạt động và được kế thừa lại như FreeBSD hay OpenBSD
   -	macOS được phát triển từ đầu theo BSD tuy nhiên đã thay đổi phần lớn theo thời gian. Ngày nay nó chỉ được coi là *nix
3. Alpine vs Ubuntu?
4. VNC


# Thực hành:
## Bước 1: Tạo một container ubuntu mới và chạy nó dưới quyền root
    docker run -d -t ubuntu
    docker ps                         //để lấy container_id
    docker inspect [container_id]     //để biết IP của container
    docker exec -u root -t - /bin/bash
## Bước 2: Cài TightVNC và Xfce
    apt install tightvncserver xfce4 xfce4-goodies
## Bước 3: Sửa file xstartup của vnc
    nano root/.vnc/xstartup
    startxfce4 &                      //thêm vào trước export
    chmod +x root/.vnc/xstartup
## Bước 4: Chạy vncserver (do chưa đặt biến môi trường USER nên phải đặt đầu lệnh)
    USER=root vncserver
## Bước 5: Mở vncviewer, truy cập vào IP container đã biết ở trên với cổng 5901
![image](https://github.com/Silwee/KTPM-II-23-24/assets/100249792/04928aeb-780e-4df3-91f3-03cd3b282a82)
