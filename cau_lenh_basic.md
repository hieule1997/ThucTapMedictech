#Các câu lệnh trong linux
**Các lệnh xử lí tập tin**
    ls -liệt kê nội dung thư mục hiện tại  
    `ls -al -liệt kê có định dạng và cả tập tin ẩn`  
    cd dir -chuyển từ thư mục hiện tại sang dir  
    `cd -chuyển từ thư mục hiện tại về thư mục riêng`  
    pwd -hiện thư mục hiện tại  
    `mkdir dir -tạo thư mục dir`  
    rm file -xóa tập tin file  
    `rm -r dir -ép xóa thư mục dir`  
    rm -f file -ép xóa tập tin file  
    `rm -rf dir -ép xóa thư mục dir *`  
    cp file_1 file_2 -chép tập tin file_1 sang file_2    
    `cp -r dir_1 dir_2 -chép thư mục dir_1 sang dir_2 tạo dir2 nếu chưa tồn tại`  
    mv file_1 file_2 -đổi tên hoặc di chuyển tập tin file_1 thành file_2;Nếu file_2 là một thư mục có sẵn, di chuyển file_1 vào thư mục file_2  
    `ln -s file link -tạo liên kết biểu tượng link đến tập tin file`  
    touch file -tạo hoặc cập nhật tập tin file  
    `cat > file -Nhập từ bàn phím (đầu vào chuẩn -standard input) vào tập tin file mới`  
    more file -hiện nội dung tập tin file
    `head file -hiện 10 dòng đầu của tập tin file`  
    tail -f file -hiện nội dung của tập tin file và cập nhật liên tục với 10 dòng cuối  
 
**Quản lí tiến trình**  
    ps -hiện những tiến trình đang hoạt động tích cực  
    `top -hiện tất cả các tiến trình đang hoạt đông`  
    kill pid -ép thoát tiến trình có mã pid  
    `killall proc -ép thoát các tiến trình tên proc`  
    bg -hiện các công việc đã kết thúc hoặc đang chạy nền,tiếp tục một công viêc đã tạm ngừng  
    `fg -ngừng chauj nền(chuyển sang foreground) với công việc gần đây nhất`  
    fg n - ngừng chạy nền với công việc n  
    
**Quyền sử dụng tập tin**  
    chmod octal file -thay đổi quyền sử dụng của tập tin file thành octal. Mỗi chữ số ứng với từng tài khoản có được bằng các số sau:
    * 4 - đọc (r)  
    * 2 - ghi (w)  
    * 1 - thực thi (x)  
    
**SSH**  
    ssh user@host -kết nối đến máy host với tài khoản user  
    ssh -p port user@host -kết nối đến máy host qua cổng port với tài khoản user  
    ssh-copy-id user@host -thêm khóa công cộng của tài khoản user vào máy host để thiết lập đăng nhập không cần mật khẩu(đăng nhập có khóa)  
    