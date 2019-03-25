# Tìm hiểu về linux
##### Giới thiệu file system
* Thư mục gốc: /  
    Đây là thư mục có cấp thấp nhất, nó chứa tất cả những thư mục và file lam việc  
    của VPS. Tại thư mục này chỉ có user root mới có quyền làm việc trên nó  
    Lệnh chuyển tới `cd/`
* /bin  
    Đây là thư mục chứa các tập tin thực thi các lệnh linux như lệnh ls,nano,grep... ngoài ra nó cũng  
    chứa các lệnh do user tự định nghĩa. Tất cả người dùng trên hệ thống đều có quyền sử dụng lệnh này.  
    Lệnh chuyển tơi: `cd/bin`.
* /sbin  
    Thư mục chứa các tập tin thực thi của hệ thống, nó cũng có chức năng giống như thư mục bin, tuy  
    nhiên sự khác biệt đó là nó chỉ dành cho người quản trị viên dùng để quản trị hệ thống. Các thư mục thực thi đó là iptables, reboot, fsck, ...  
    Lệnh chuyển tơi: `cd/sbin`  
* /etc  
    Thư mục chứa các tập tin *cấu hình* của hệ thống và chạy cho tất cả các chương trình trên linux,cấu hình  
    cho chương trình khởi động hoặc các chương trình đơn lẻ khác như `/etc/ssh/sshd_config` , `etc/my.cnf`.
    Lệnh chuyển tới: `cd/etc`  
* /dev  
    Chứa các tập tin thiết bị như thiết bị đầu cuối USB, hoặc bất kì một thiết bị nào được gắn vào hệ thống, ví  
    dụ `/dev/sda`, `dev/usbmon0`.  
    Lệnh chuyển tới: `cd/dev`  
* /proc  
    Thư mục chứa thông tin về tiến trình của hệ thống, các tập tin này sẽ chứa các tiến trình đang chạy.  
    Lệnh chuyển tới `cd/proc`  
* /var  
    Đây là các tập biến đổi, dung lượng của nó sẽ lớn dần theo thời gian. Ví dụ các tin hệ thống như log,  
    tập tin lưu trữ dữ liệu,thư điện tử,hàng đợi,...  
* /tmp  
    Thư mục chứa các tập tin tạm thời, các tập tin tạm sẽ bị xóa khi hệ thống khởi động lại.  
    Lệnh chuyển tới `cd/tmp`  
*  /usr  
    Chứa các tập tin thực thi,thư viện,tài liệu mã nguồi cho các chương trình mức độ thứ hai.  
    Lệnh chuyển tới `cd/usr`  
* /home  
    Thư mục của người dùng,chứa các tập tin dùng cho hệ thống theo người dùng.Ví dụ /home/freetuts.  
    Lệnh chuyển tới `cd/home`  
* /boot  
    Chứa các tập tin của chương trình khởi động máy.  
    Lệnh chuyển tới `cd/boot`  
* /lib
    Chứa các tập tin thư viện của hệ thống, các tập tin này hỗ trợ cho các tập tin trong thư mục `/bin` và  
    `/sbin`.  
    Lệnh chuyển tới `cd/media`  
* /opt  
    Chứa các ứng dụng tùy chọn hoặc thêm.  
    Lệnh chuyển tới `cd/opt`  
* /media  
    Chứa các tập tin thiết bị tháo lắp, ví dụ `/media/cdrom cho CD-ROM`;`/media/floppy` cho ổ đĩa mềm;  
    `/media/cdrecorder` cho ổ đĩa ghi CD.  
* /srv  
    Chứa dữ liệu liên quan đến dịch vụ trên máy chủ.  
    Lệnh chuyển tới `cd/srv`  
    

