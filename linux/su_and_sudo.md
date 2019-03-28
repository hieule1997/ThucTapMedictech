## su  

Lệnh này được sử dụng để đăng nhập tài khoản root  
`su` (có nghĩa là "người dùng thay thế" hoặc "người dùng chuyển đổi")  
Thực hiện chính xác điều đó, nó bắt đầu một thể hiện shell khác với đặc quyền của người dùng đích.  
Để đảm bảo bạn có quyền làm điều đó, nó sẽ hỏi bạn mật khẩu **của người dùng mục tiêu**. Vì vậy, để trở thành root  
bạn cần biết mật khẩu root. Nếu nhiều người dùng trên máy tính của bạn, những người cần chạy lệnh dưới dạng root,tất  
cả họ đều cần biết mật khẩu gốc -lưu ý rằng nó sẽ cùng là một mật khẩu.Nếu bạn cần thu hổi quyền
quản trị từ một trong những người dùng, bạn cần thay đổi mật khẩu gốc và chỉ cho phpes những người cần truy cập -lộn xộn.  
Su cho phép truy cập vào các tài khoản của người dùng khác

## sudo  

Nó sử dụng một tệp cấu hình (/etc/sudoers) liệt kê những người dùng nào có quyền đối với các hành động cụ thể(chạy các lệnh dưới dạng root)  
Khi được gọi, nó yêu cầu *mật khẩu của người dùng đã bắt đầu*. Để thu hồi đặc quyền quản trị từ một người, bạn chỉ càn chỉnh sửa tệp cấu hình  
(hoặc xóa người dùng khỏi nhóm được liệt kê trong cấu hình đó). Điều này dẫn đến việc quản lý quyền ưu tiên hơn nhiều.    

```
Sudo để người dùng sử dụng tài khoản của họ để chạy câu lệnh hệ thống.Su thì bắt buộc người dùng chia sẻ root password với các người dùng khác.
Đó chính là lý do tại sao sudo không khởi động bất kì một cửa sổ shell mới nào
```  
Sudo là một bộ nhị phân setuid ở thư mục root, nó thực hiện các lệnh root thay cho người dùng được ủy quyền và người dùng cần phải nhập mật khẩu  
của họ để thực hiện hệ thống bằng `sudo`  