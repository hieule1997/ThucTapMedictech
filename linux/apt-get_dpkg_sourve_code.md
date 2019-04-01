# Ba cách cài đặt trong Ubuntu  

#### 1.dpkg  

**dpkg** là phần mềm làm nền tảng cho các hệ thống quản lý gói tin trên hệ điều hành tự do nguồn mở Debian và các phát sinh từ nó  
`dpkg` được sử dụng để cài đặt, gỡ bỏ, và cung cấp thông tin về các gói `.deb`  
`dpkg` (Debian Packge) là một công cụ cấp thấp. APT(Advanced Packaging Tool), một công cụ cấp cao hơn, được sử dụng nhiều hơn `dpkg`  
vì nó có thể tìm được các gói tin từ xa và giải quyết các gói tin có quan hệ phức tạp, chẳng hạn như các gói tin phụ thuộc.  

**Sử dụng dpkg**  
```dpkg -i debFileName```  

Với debFileName là tên của gói cài đặt.
Danh sách các gói cài đặt có thể được có với: 

```dpkg -l [optiona pattern]```  

Để gỡ bỏ một gói tin: 

```dpkg -r packagename```   

**dpkg-source:** đóng gói và giải nén các tập tin mã nguồn của một gói Debian.  
**dpkg-gencontrol:** đọc thông tin từ một mã nguồn cây Debian giải nén và tạo ra một gói điều khiển gói nhị phân, tạo ra một mục  
cho vấn đề này Debian/file.  
**dpkg-shlibdeps:** tính toán các phụ thuộc của chạy đối với các thư viện với.  
**dpkg-genchanges:** đọc thông tin từ một nguồn cây Debian giải nén mà sau khi xây dựng tạo ra một tập tin điều khiển (.changes).  
**dpkg-buildpackage:** là một kịch bản kiểm soát có thể được sử dụng để xây dựng các gói tự động.  
**dpkg-distaddfile:** bổ sung một file đầu vào debian / tập tin.  
**dpkg-parsechangelog:** rđọc các tập tin thay đổi (changelog) của một nguồn cây Debian giải nén và tạo ra một đầu ra chuẩn bị thuận tiện với các thông tin cho những thay đổi đó.  

#### 2.apt-get  

APT là một dự án lớn, ban đầu bao gồm một giao diện đồ họa. Nó dựa trên một thư viện chưa ứng dụng cốt lõi, và **apt-get** là giao diện đầu  
tiên - dòng lệnh - được phát triển trong dự án.**apt** là một giao diện dựa trên dòng lệnh cung cấp bởi APT mà khắc phục một số sai lầm
trong thiết kế của **apt-get**  

**Lệnh cài đặt**  
```sudo apt-get install ten-goi```  

Lệnh này sẽ cài đặt một gói mới
```sudo apt-get buil-dep tên-gói```  

Lệnh này sẽ tìm kiếm trên kho và cài đặt những gói phụ thuộc cần thiết để có thể cài đặt được gói từ mã nguồn. Nếu gói không có trong kho,
lệnh sẽ trả về một lỗi.  
apt-get chấp nhận một danh sách các gói làm tham số cài đặt, ví dụ:  
```sudo apt-get install tên-gói-1 tên-gói-2 tên-gói-3 ...```  

Dùng tùy chọn -s để giả lập một hành động. "sudo apt-get -s intall tên-gói" sẽ giả lập việc cài đặt một gói, cho bạn biết nơi gói sẽ được cài đặt  
và cấu hình nó.

**Lệnh tìm gói**  
Lệnh này sẽ giúp chúng ta tìm 1 gói, hoặc 1 chương trình nào đó trong ubuntu. Ví dụ tôi không nhớ chính xác tên gói cài đặt  
của chương trình amrok làm sao để cài đặt bằng lệnh, việc này thực hiện rất đơn giản  

```sudo apt-cache search tham số```  

Tham số có thể là tên chương trình hay là ghi chú .... nó sẽ trả về tên gói + ghi chú kế bên sau đó bạn chỉ cần sử dụng lệnh apt-get install để cài đặt 

**Lệnh bảo quản**  
```sudo apt-get update```  

Chạy lệnh này sau khi thay đổi /etc/apt/sources.list hoặc /etc/apt/preferences. Để biết thêm về /etc/apt/preferences  
Chạy lệnh này thường xuyên giúp danh sách nguồn của bạn được cập nhật. Nó tương đương với "Reload" trong Synaptic hoặc "Fetch updates" trong Adept.  

```sudo apt-get upgrade```  

Lệnh này nâng cấp tất cả các gói đã cài đặt. Nó tương đương với "Mark all upgrades" trong Synaptic.  
```sudo apt-get dist-upgrade```  

Lệnh này nâng cấp toàn hệ thống tới một phiên bản mới hơn. Nó tương tự như ở trên, ngoại trừ thêm đánh dấu thêm "smart upgrade". Nó báo APT  
 sử dụng hệ thống giải quyết xung đột thông minh,
 và nó sẽ thử nâng cấp những gói quan trọng nhất. Đây không phải là cách được khuyên để nâng cấp bản phân phối,  
 
 ```sudo apt-get check```  
 Lệnh này là một công cụ để chuẩn đoán. Nó không cập nhật danh sách nguồn, mà chỉ kiểm tra lỗi phụ thuộc.  
 ```sudo apt-get -f install```  
 Lệnh này tương tự như Edit -> Fix Broken Packages trong Synaptic. Chạy nó nếu bạn nếu bạn gặp phải lỗi phụ thuộc của các gói.  
 ```sudo apt-get autoclean```  
 Lệnh này gỡ bỏ các tệp cài đặt .deb đã cũ trong hệ thống của bạn. Phụ thuộc vào thói quen cài đặt của bạn, xóa bỏ các tệp trong /var/cache/apt/archives có thể thu hồi một lượng không gian đĩa đáng kể.

```sudo apt-get clean```  
Lệnh này tương tự như trên nhưng nó sẽ xóa bỏ tất cả các gói trong nơi lưu trữ. Nó không tốt lắm nếu bạn đang sở hữu một đường truyền Internet chậm, vì khi cài đặt sẽ phải tải lại các gói (đáng ra có sẵn tại nơi lưu trữ).

Nơi lưu trữ các gói đã được cài đặt là /var/cache/apt/archives. Lệnh:  
```du -sh /var/cache/apt/archives```  
sẽ cho biết dung lượng các gói được lưu trữ. 



