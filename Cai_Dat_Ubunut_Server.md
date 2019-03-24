# I.Giới thiệu về Ubuntu server 16.04  
#### 1.Tổng quan chung về HDH Ubuntu
* Ubuntu là một hệ điều hành máy tính dựa trên Debian GNU/Linux, một bản phân phối Linux thông dụng.  
* Bản phát hành đầu tiên của Ubuntu là vào 20 tháng 10 năm 2004, bắt đầu bằng việc tạo ra một nhánh tạm thời của dự án Debian Linux.  
* Mục đích của Ubuntu bao gồm việc cung cấp một hệ điều hành ổn định, cập nhật cho người dùng bình thường, và tập trung vào sự tiện dụng và dễ dàng cài đặt.  
* Ubuntu được tài trợ bởi Canonical Ltd (chủ sở hữu là một người Nam Phi Mark Shuttleworth). Thay vì bán Ubuntu, Canonical tạo ra doanh thu bằng cách bán hỗ trợ kĩ thuật.  
* Trong quá trình phát triển, dự án Ubuntu đã cho ra đời nhiều phiên bản khác nhau của Ubuntu, như Ubuntu Desktop cho máy tính để bàn, Ubuntu Netbook Remix cho netbook (đã ngừng phát triển), Ubuntu Server cho các máy chủ, Ubuntu Business Desktop Remix cho các doanh nghiệp, Ubuntu for Android và Ubuntu for Phones cho các thiết bị di động.  
#### 2. Các tính năng nổi bật  
* Ubuntu là phần mềm mã nguồn mở tự do, có nghĩa là người dùng được tự do chạy, sao chép, phân phối, nghiên cứu, thay đổi và cải tiến phần mềm theo điều khoản của giấy phép GNU GPL.  
* buntu kết hợp những đặc điểm nổi bật chung của hệ điều hành nhân Linux, như tính bảo mật trước mọi virus và malware, khả năng tùy biến cao, tốc độ, hiệu suất làm việc, và những đặc điểm riêng tiêu biểu của Ubuntu như giao diện bắt mắt, bóng bẩy, cài đặt ứng dụng đơn giản, sự dễ dàng trong việc sao lưu dữ liệu và sự hỗ trợ của một cộng đồng người dùng khổng lồ.
# II.Cách cài đặt ubuntu server 16.04 64 bit trên VMware  
#### 1. Cấu hình tối thiểu  

<img src="https://cloud.githubusercontent.com/assets/18635054/14889327/87ee89c8-0d88-11e6-884a-b7dd88d35149.png">
  
#### 2. Các bước cài đặt  

**Bước 1: Chọn ngôn ngữ cho Ubuntu Server**  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889350/9bdca47e-0d88-11e6-80d7-a0709f9a9c9f.png" width="801" height="369">  

**Bước 2: Chọn `Install Ubuntu Server` để bắt đầu quá trình cài đặt**  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889352/9edd833c-0d88-11e6-9f4e-092ecd5d08d4.png" width="801" height="369">  

**Bước 3: Chọn ngôn ngữ cài đặt**  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889472/280ab3d2-0d89-11e6-8660-b18ee207a391.png" width="801" height="369">  

**Bước 4: Chọn time zone và khu vực**  

<img src="https://cloud.githubusercontent.com/assets/18635054/14889477/2a66885e-0d89-11e6-9f53-364f15c55115.png" style="max-width:100%;">  

**Bước 5: Nếu khu vực vừa chọn không tương thích với ngôn ngữ đã chọn,máy sẽ báo phải chọn lại khu vực**  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889514/4641a9e6-0d89-11e6-9cbc-f5b53989f84f.png" width="801" height="369">  

**Bước 6: chọn `No` nếu không muốn dò bàn phím và tiến hành chọn kiểu bàn phím thủ công**  

<img src="https://cloud.githubusercontent.com/assets/18635054/14889517/4a5793ec-0d89-11e6-9aa4-13a52ca0a58f.png" style="max-width:100%;">  
 
<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889519/503d2952-0d89-11e6-9ffb-77204e3937df.png" width="801" height="369">  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889588/9dac6edc-0d89-11e6-95f9-602c3bb34ec1.png" width="801" height="369">  

**Bước 7: DHCP báo không thể cấp lại địa chỉ IP động, lúc này phải chọn cấu hình bằng tay.Chọn `configure network manually`**  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889591/a4e6b2de-0d89-11e6-8cec-22df86372e78.png" width="801" height="369">  
  
<img src="https://cloud.githubusercontent.com/assets/18635054/14889624/c6fa2ba8-0d89-11e6-9e6d-a1a99eb41d8c.png" style="max-width:100%;">

**Bước 8:Cấu hình địa chỉ IP,netmask,gateway,name server(có thể để trống),hostname,domain name(có thể để trống).**  
 
<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889629/cbc01b84-0d89-11e6-9b4c-def629ac9044.png" width="801" height="369">  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889652/e89e827c-0d89-11e6-8e77-d1c1f7aaf5b9.png" width="801" height="369">  

<img src="https://cloud.githubusercontent.com/assets/18635054/14889673/f9864840-0d89-11e6-8804-d8fb844a5652.png" style="max-width:100%;">  

<img src="https://cloud.githubusercontent.com/assets/18635054/14889673/f9864840-0d89-11e6-8804-d8fb844a5652.png" style="max-width:100%;">  

<img src="https://cloud.githubusercontent.com/assets/18635054/14889683/027a05f4-0d8a-11e6-9f41-a7ec7e47eef6.png" style="max-width:100%;">  

<img src="https://cloud.githubusercontent.com/assets/18635054/14889683/027a05f4-0d8a-11e6-9f41-a7ec7e47eef6.png" style="max-width:100%;">  

**Bước 9:Tạo user và password**  
* Không giống một số hệ điều hành Linux khác như CentOS, Ubuntu không cho phép người dùng đặt mật khẩu và sử dụng ngay tài khoản `root`. Thay vào đó, chúng ta phải tạo một tài khoản mới rồi sau khi cài đặt xong mới có thể dùng nó để đăng nhập sang tài khoản root. Điều này góp phần tăng tính bảo mật cho HĐH Ubuntu Server.  

<img src="https://cloud.githubusercontent.com/assets/18635054/14889743/385c86a6-0d8a-11e6-9e86-25e2209a6764.png" style="max-width:100%;">  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889752/3ecb10f2-0d8a-11e6-93da-30b136634b9a.png" width="494" height="369">  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889752/3ecb10f2-0d8a-11e6-93da-30b136634b9a.png" width="494" height="369">  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889750/3ead6f02-0d8a-11e6-8b36-2d9c56b7e601.png" width="498" height="369">  

<img src="https://cloud.githubusercontent.com/assets/18635054/14889753/3edc56d2-0d8a-11e6-8e55-866d228a8cb2.png" style="max-width:100%;">  

**Bước 10:Server hỏi xem liệu người dùng muốn mã hóa thư mục `home` không.Chọn `No` nếu không muốn.**  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889789/6dbd0c08-0d8a-11e6-980b-7bfa015a4593.png" width="498" height="369">  

**Bước 11:Phân vùng ổ cứng cho Ubuntu**  
* Có 4 sự lựa chọn cho người dùng
* Guided - use entrie disk: Tự động phân vùng.  
* Guided - use entire disk and with set up LVM: Tự động phân vùng bằng LVM.  
* Guided - use entire disk and with set encrypted up LVM`: Tự động phân vùng và mã hóa LVM.  
* Manual: Phân vùng thủ công.  
* Nếu bạn muốn phân vùng thủ công, chia ra hai phân vùng chính  
* Phân vùng đầu tiên có định dạng ext4, thư mục root dùng để chứa dữ liệu và hệ điều hành  
* Phân vùng thứ 2 khoảng 1,1 GB có định dạng swap dùng làm Ram ảo cho hệ điều hành  
* Ở đây tôi chọn phân vùng tự động với LVM.  

<img src="https://cloud.githubusercontent.com/assets/18635054/14890749/0dfc6d8c-0d8e-11e6-822e-3cf98535b5c9.png" style="max-width:100%;">  

<img src="https://cloud.githubusercontent.com/assets/18635054/14890751/0e0f565e-0d8e-11e6-8032-d40af7bb35e5.png" style="max-width:100%;">  

<img src="https://cloud.githubusercontent.com/assets/18635054/14890753/0e36de90-0d8e-11e6-9362-2a562fb652ff.png" style="max-width:100%;">  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14890750/0dfdda96-0d8e-11e6-8db5-535f2d9f3278.png" width="495" height="369">  

<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14890750/0dfdda96-0d8e-11e6-8db5-535f2d9f3278.png" width="495" height="369">  

**Bước 12:Cấu hình HTTP proxy Server**  
* Điền vào proxy,nếu không có thì để trống.  
<img style="-webkit-user-select: none;cursor: zoom-in;" src="https://cloud.githubusercontent.com/assets/18635054/14889924/e18ae8e4-0d8a-11e6-82e5-dd2d450b97cd.png" width="496" height="369">  

**Bước 13: Cấu hình và cập nhật**  
* Có 3 sự lựa chọn
* `No automatic update`: Không tự đông cập nhật
* `Install security updates automatically`:Cấu hình cho phép tự động cập nhật
* Mange system with Landscape: Quản lý từ xa.  
* Tùy vào người sử dụng, ở đây tôi chọn "Không cho phép tự động cập nhật"  

<img src="https://cloud.githubusercontent.com/assets/18635054/14889926/e2356a62-0d8a-11e6-8e73-40081927d330.png" style="max-width:100%;">  

**Bước 14: Cấu hình cài đặt các phần mềm hỗ trợ**  
* Ấn `Space` để chọn phần mềm bạn muốn cài thêm, ở đây tôi chọn cài thêm OpenSSH Server để có thể SSH từ xa.  

<img src="https://cloud.githubusercontent.com/assets/18635054/14889928/e25f0caa-0d8a-11e6-831f-89c78d528d41.png" style="max-width:100%;">  

**Bước 15: Cài đặt boot loader(GRUB) trên ổ đĩa**   

<img src="https://cloud.githubusercontent.com/assets/18635054/14889955/fda32280-0d8a-11e6-86dc-9fac4509dbee.png" style="max-width:100%;">  

**Bước 16: Kết thúc và chonj `Continues` để reboot lại máy**  

<img src="https://cloud.githubusercontent.com/assets/18635054/14889954/fda11c4c-0d8a-11e6-919a-b73540e70593.png" style="max-width:100%;">  

Sau khi reboot lại máy, các bạn đăng nhập bằng bằng tài khoản đã tạo ở bước 9. Lúc này bạn `Continue` và máy tính sẽ tự restart vào OS ubuntu Server cho bạn 
