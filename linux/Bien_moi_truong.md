## Environment variables  

Các biến môi trường được đặt tên đơn giản theo số lượng các giá trị cụ thể và được hiểu bởi command shell, như `bash`.  
Một số các thông số được thiết lập trước bởi hệ thống, và một số khác được thiết lập bởi user bằng command line hoặc  
trong khi khởi động. Một biến môi trường thực sự không qua một chuỗi kí tự chứa thông tin được sử dụng bởi một hoặc  
nhiều ứng dụng. Có một số cách để xem các giá trị của các biến môi trường hiện tại đang được thiết lập, sử dụng command  
`set`, `evn`, `exxport`.  

Mặc định, các biến được tạo ra trong script chỉ có sẵn cho shell hiện đang chạy. Tất cả các chương trình con(sub-shell) sẽ  
không có quyền truy cập vào các biến đã được thiết lập hoặc sửa đổi. Cho phép các chương trình con được xem các giá trị,  
yêu cầu sử dụng lệnh `exxport`.  

|   Task    |   Command     |  
|-----------|---------------|  
|Show the value of a specific variable| echo $SHELL |  
|Export a new variable value| export VAR=value|  
|Add a variable permanently | Add the line export VAR=value to ~/.bashrc|  

`HOME` là biến môi trường đại diện cho thư mục `home`.Command `cd` sẽ mặc định về thư mục home.  

Dấu `~` là viết tắt của `$HOME`  

Biến môi trường `PATH` là một danh sách được sắp xếp theo thứ tự các thư mục được quét khi một lệnh được đưa ra để tìm  
chương trình hoặc tệp lệnh thích hợp để chạy. Mỗi thư mục trong đường dẫn được phân cách bằng dấu hai chấm. Tên thư mục trống  
cho biết thư mục hiện tại, tại bất kì thời điểm nào.  
```
$ export PATH=$HOME/bin:$PATH
$ echo $PATH  
/home/trang/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games  
```  
Biến môi trường `PS` được sử dụng để tùy chọn các chuỗi ghi chú của bạn trên cửa sổ terminal để hiển thị ra thông tin bạn  
muốn. `PS1` là biến prompt chính để điều khiển command line prompt trong như thế nào. Các kí tự đặc biệt trong PS1:  

|   Character   |   Usage   |  
|---------------|-----------|  
|   \u          | User name |  
|   \h          | Host name |  
|   \w          | Curent working directory |  
|   !           | History number of this command |  
|   \d          | Date       |  

## alias

#### Thiết lập và quản lí các alias  
alias được chia thành 2 loại là permanent alias và temporarily alias. Temporarily alias sẽ mất đi mỗi khi phiên làm việc trên bash shell  
của bạn kết thúc(tắt cửa sổ terminal, logout hay restart máy). Còn permanent alias sẽ không bị mất đi trừ khi bạn xóa nó.  
* Temporarily alias  
    Để thêm mới 1 alias ta dùng lệnh  
    ```alias alias_name=\aliased_command --options\```    
    Để xóa 1 temporarily alias  
    ```unalias alias_name```  
* Permanent alias  
Đối với các permanent alias, chúng sẽ được định nghĩa và lưu trong file `~/.bashrc`  
hoặc `~/.bash_profile`. Ngoài ra ta cũng có thể lưu riêng các alias ra 1 file khác ví dụ `~/.alias`. Khi đó cần thêm đoạn script sau vào file `~/.bashrc`  

```if[-e $HOME/.alias];then  [-n "$PS1"] &&.$HOME./alias  fi```  
    
Việc tạo ra 1 alias trong các file này cũng hoàn toàn tương tự như khi bạn tạo 1 temporarily alias.  
Sau khi thêm các alias và lưu file lại, để các alias mới có thể hoạt động ngay tại phiên làm việc hiện tại, bạn dùng lệnh  

```source~/.bashrc```  

Hoặc  

```.~/.bashrc```  
Nếu bạn lưu các alias trong file `.bash_profile` hoặc `.bash_alias` thì cũng  tương tự.  
Để xem danh sách các alias  
```alias```  
Lúc này màn hình terminal sẽ liệt kê tất cả các alias đang có bao gồm cả permanent và temporarily alias dưới dạng:

```
alias egrep=\'egrep --color=auto\'  
alias fgrep=\'fgrep --color=auto\'  
alias grep=\'grep --color=auto\'  
alias h=\`history\'  
alias in=\'sudo apt-get install\'  
alias install=\'sudo apt-get install\' 
```  

**alias quản lí các gói**  
```

alias ai=\'sudo apt-get install\'  
alias ar=\'sudo apt-get remove\'  
alias au=\'sudo apt-get update\'  
alias aug=\'sudo apt-get upgrade\'  
```  
**alias file và thư mục**  
```
alias ..=\'cd ..\'  
alias ...=\'cd ../..\'  
alias ....=\'cd ../../..\'  
alias du=\'du -h\'  
alias df=\'df -h\'  
alias l.=\'ls -d .* --color=auto\'  
alias ls=\'ls -F --color=auto\'  
alias cl=\'clear && ls\'  #Xóa màn hình và hiển thị file,thư mục con       
```
**Một số loại alias hữu ích khác**  
```
alias e=\'exit\'  
alias s=\'sudo\'  
alias nnb=\'nano ~/.bashrc\'  #Sửa file alias
alias rlb=\'. ~/.bashrc\'     #Load lại file alias
alias h=\'history\'
```  
**Alias trong Git**  
Riêng đối với git, ta có thể tạo và xóa các alias tượng tự như trên.Tuy nhiên git cũng có cách cài đặt những alias theo cách riêng.  
Đây là 1 vài ví dụ về thêm mới các alias cho git  
```
git config --global alias.co checkout  
git config --global alias.br branch  
git config --global alias.ci commit  
git config --global alias.st status  
git config --global alias.last \'log -1 HEAD\'  
```  
Để kiểm tra các alias của git ta dùng lệnh  
```git config --get-regexp alias```