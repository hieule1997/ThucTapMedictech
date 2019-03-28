## Hostname  
Hostname là chương trình sử dụng để thiết lập hoặc hiển thị tên máy chủ, tên miền hoặc tên nút hiện tại của hệ thống Linux  
Những tên này được sử dụng bởi các phần mềm network để xác định trên hệ thống mạng.  

**1 Kiểm tra hostname hiện tại của hệ thống**  
```
    root@ubuntu:~# hostname  
    ubuntu
```  
**2 Thay đổi hostname vĩnh viễn**  
Bạn cần reboot lại máy chủ hoặc kết nối lại SSH  
```
# change hostname
root@ubuntu:~# hostname vinasupport.com  
root@ubuntu:~# hostname  
vinasupport.com     #hostname đã được thay đổi
```  
**3 Sửa hostname tạm thời**  
```
root@ubuntu:~# hostnamectl set-hostname dlp.srv.world  
#show settings  
root@ubuntu:~# hostnamectl  
 Static hostname: vinasupport  
Transient hostname: vinasupport.com  
         Icon name: computer-vm  
           Chassis: vm  
        Machine ID: 418d62ba5b904acf99b67e26594db71e  
           Boot ID: 41d92864958c40918567663fe2345baa  
    Virtualization: oracle  
  Operating System: Ubuntu 16.04.4 LTS  
            Kernel: Linux 4.13.0-36-generic  
      Architecture: x86-64  
```  
#### Một số command làm việc với hostname của linux  
VD1: hiển thị hostname hiện tại của hệ thống  
`$ hostname`  
VD2: hiển thị địa chỉ IP của máy chủ  
`$ hostname -i`  
VD3: hiển thị Domain Name  
`$ hostname -d`  
VD4: hiển thị hostname(Ở định dạng ngắn gọn):
`$ hostname -s`  

#### File host là gì?
File host là một tập tin lưu trữ thông tin IP của các máy chủ và tên miền(domain) được trỏ tới. Nó có thể được  
gọi là một DNS nhỏ trên máy tính của bạn.File host giúp cho các hệ điều biết được IP của máy chủ nơi một tên miền  
cụ thể nào đó được quản lí.  
#### thay đổi host name trong centos

**Bước 1: Đăng nhập**  
Ssh tới vps của bạn bằng tài khoản root.  
```ssh root@server```  

**Bước 2: Thay đổi hostname**  
Bạn có thể dùng lệnh hostname <tên hostname mới> để thay đổi hostname.  
Ví dụ:  
```hostname server1.kienthuclinux.com```  
Tuy nhiên khi thay đổi như trên chỉ là tạm thời khởi động lại hostname sẽ trả về giá trị cũ.  
Ta cần thao tác thêm 1 số bước sau.  
**Bước 3: sửa file /etc/hosts**  
```vi /etc/hosts```  
thay đổi hostname cũ thành hostname mới và save lại.  
**Bước 4: sửa file /etc/sysconfig/network**  
```vi /etc/sysconfig/network```  
thay đổi hostname cũ thành hostsname mới, sau đó tiến hành save lại.  
**Bước 5: kiểm tra hostname.**  
```hostname```  

#### Sửa file hosts trên Linux(Ubuntu)  
```angular2
    sudo -i gedit /etc/hosts  
    sudo vim /etc/host  
    sudo nano /etc/hosts  
```