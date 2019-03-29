# Cấu hình mạng cho Ubuntu server 16.04 LTS  

### Các dịch vụ liên quan  

Để cấu hình mạng cho Ubuntu kết nối được internet chúng ta cần chú ý các dịch vụ sau:  
 * networking.service : nhiệm vụ của nó là up hay down các interface (card mạng) được liên kết ở trong  
 file **/etc/network/interfaces.**.  
 
 * NetworkManager.service: là một dịch vụ cho phép chúng ta quản lí network. Nó cung cập cho giao diện đồ họa và cả giao diện command line (lệnh **nmcli**) để chúng ta cấu hình network.  
 * systemd-network.service: cũng là một dịch vụ cho phép chúng ta quản lý network. Nó mới hơn  
 NetworkManager.service là một phần của **systemd**. Nó buộc chúng ta phải edit các file cấu hình kèo them mới có thể cấu  
 hình network cho hệ thống.  
 
#### Ubuntu Desktop 16.04 :  
* Dịch vụ **networking.service** và NetworkManager.service sẽ được active.  
* Còn dịch vụ systemd-networkd.service sẽ được load sẵn nhưng không active.  
 
#### Ubuntu Server 16.04 LTS :  
* Chỉ có mỗi dịch vụ **networking.service** được acitve thôi  
* Dịch vụ **NetworkManager.service** sẽ không được cài đặt sẵn.  
* Còn dịch vụ **systemd-networkd.service** sẽ được load sẵn nhưng không active nếu bạn cần dùng thì active nó lên.  

**Tóm tắt lại thì tên card mạng được đặt theo kiểu:**  
Hai kí tự đầu đại diện cho kiểu card mạng:  
* en - Ethernet  
* sl - serial line IP (slip)  
* wl - wlan  
* ww - wwan  

Kiểu tên:  
* p - pci greographical location (pci-e slot)  
* s - hotplug slot index number  
* o - onbroad cards
* f - function (used for cards with more than one port)  
* u - USB port  
* i - USB port interface

#### Giới thiệu công cụ ifconfig  

Công cụ ifconfig trong Linux có tác dụng giống như công cụ ipconfig trong Windows vậy. Để tìm hiểu thêm về công cụ này bạn  
có thể sử dụng lệnh:  
```man ifconfig```  

Để xem thông tin tất cả card mạng trong hệ thống ta dùng lệnh:  
```if config -a```  

Để up hoặc down card mạng nào đó ta có thể sử dụng lệnh:  
```ifconfig <tên card mạng> up  ifconfig <tên card mạng> down```  

Để thêm hoặc xóa địa chỉ ip cho một card mạng ta có thể sử dụng lênh:  
```ifconfig <tên card mạng> add <địa chỉ ip>  ifconfig <tên card mạng> del <địa chỉ ip>```  

#### Cấu hình mạng cho Unbuntu Server 16.04 LTS bằng cách sửa file interfaces  
Như đã giới thiệu trong phần trên. Khi hệ thống khởi động dịch vụ **networking.service** nó sẽ đọc file **/etc/networking/interface**  
để lấy thông tin card mạng và khởi động nó lên. Chúng ta có thể sử dụng trình soạn thảo để cấu hình mạng cho Ubuntu như sau:  

```
# Card mạng loopback  
auto lo  
iface lo inet loopback  

# Card mạng chính mà chúng ta muốn dùng  
auto enp3s0  
# comment dòng  
#iface ens3 inet dhcp 
# thêm vào các dòng sau  
iface enp3s0 inet static  
address 192.168.1.30     # IP address  
network 192.168.1.0      # network address  
netmask 255.255.255.0    # subnet mask  
broadcast 192.168.1.255  # broadcast address  
gateway 192.168.1.1      # default gateway  
dns-nameservers 8.8.8.8  # name server  
```  

#### Cấu hình mạng cho Ubuntu bằng công cụ nmcli  

Như đã giới thiệu ở phần trên. Công cụ nmcli(Network Manager Command Line Interface) là một phần đi kèm với dịch vụ  
**NetworkManager.service**. Nó cho phép chúng ta cấu hình mạng cho **Ubuntu** bằng giao diện dòng lệnh. Tùy nhiên nếu chúng ta  
có cài đặt và sử dụng NetworkManger thì thông thường là cấu hình bằng giao diện đồ họa luôn cho dễ nhìn.  

Mặc định thì **NetworkManager** chỉ được cài đặt trên **Ubuntu Desktop** chứ không được cài đặt trên **Ubuntu Server**.  
```$ man nmcli```  

Để xem các connection:  
```$ nmcli c s  ```  

Để xem trạng thái các card mạng:  
```$ nmcli d s```  

Để connect hay disconnect card mạng:  
```nmcli device disconnect enp3s0```  ```nmcli device connect enp3s0```  

#### Cấu hình mạng cho Ubuntu bằng systemd-netword.  

Để cấu hình mạng cho **Ubuntu**  bằng **systemd-netword**. Chúng ta sẽ tạo ra các file có dạng **<độ ưu tiên>-<tên>.network** đặt  
trong **/etc/systemd/network/.**  

Nhớ là sử dụng **systemd-networkd.service** thì phải start nó lên và tắt NetworkManager.service đi và ta chỉ cần 1 trong 2 thôi.  
Và bật thêm dịch vụ **systemd-resolved.service** để sử dụng **DNS** do **DHCP** cấp.  

#### Hướng dẫn đặt địa chỉ IP tĩnh trên Ubuntu Server  

Đầu tiên, các bạn khởi động hdh UBUNTU SERVER lên, login vào hdh bằng **Username** và **Password** của bạn!  
<img src="/img/4.png">  

