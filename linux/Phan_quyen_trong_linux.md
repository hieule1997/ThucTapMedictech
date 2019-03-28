# Phân quyền trong linux  
#### Nhóm phân quyền  
 * Owner: chỉ cấp quyền cho chủ sở hữu của file.  
 * Group: chỉ cấp quyền cho nhóm sở hữu của file.  
 * Other: cấp quyền cho những người dùng và nhóm không thuộc 2 nhóm trên.  
 
#### File Permissions  
Trong Linux và Unix, mỗi file đều có một user sở hữu gọi là owner. Mỗi file cũng sẽ có một group sở hữu, những người  
trong group này có các permision nhất định: read, write và execute.  

|   Command    |        Result      |  
|--------------|--------------------|  
|   chown      | Thay đổi người sở hữ file và thư mục |  
|   chgrp      | Thay đổi group sở hữu   |  
|   chmod      | Thay đổi permision trên file hoặc thư mục |  

File có 3 kiểu permision: read(r), write(w), execute(x). Chúng thường được biểu diễn theo thứ tự `rwx`. Các permision  
này ảnh hưởng tới các nhóm của người sở hữu: user(u),group(g),và others(o). Kết quả là bạn có 3 nhóm như sau:  

|   rwx    |   rwx |   rwx |  
|----------|-------|-------|  
|   u:     |   g:  |    o  |  


**`Lệnh chmod`**  
```
    chmod [option] [permission] [name file/directiory]  
```  
Phần `permision`  có 3 kiểu:  
    * kiểu kí tự (rw-rw-r--)  
    * kiểu ugo: Phân quyền cho từng đối tượng(u+x:user thêm quyền thực thi)  
    * kiểu số: ví dụ rwxrw-r = 764  
    
**Một số quy ước cho kiểu ugo**  

|   Operator    |            |  
|---------------|----------- |  
|       +       | Thêm quyền |  
|       -       | Bỏ quyền   |  
|       =       | Gán quyền  |  

|   Owner       |            |  
|---------------|------------|  
|   a           |   u+g+o    |  
|   u           | user owner |
|   g           | group owner|  
|   o           | other user |  

Ví du:
    
```chmod a=-,u+rwx,g+rwsx,u-w```  
Phân tích lệnh trên: đầu tiên bỏ toàn bộ quyền cho cả 3 nhóm(u,g,o), sau đó thêm quyền rwx cho user sở hữu,thêm quyền  
rwsx cho group sở hữu, sau đó lại bỏ quyền `w` cho user 
#### Loại phân quyền  
   Với một file, có 3 loại phân quyền cơ bản như bảng sau:  
     
| Tên quyền | Kí hiệu | Dạng số |       Mô tả        |  
|-----------|---------|---------|--------------------|    
|   Read    |    r    |    4    |   Quyền đọc file   |    
|   Write   |    w    |     2   |   Quyền ghi file   |   
|  Exxecute |    e    |     1   | Quyền thực thi file|   
    
Ngoài ra có một vài phân quyền đặc biệt sau:  

|   Tên quyền   | Kí hiệu  | Dạng số  |                                Mô tả                      |  
|---------------|----------|----------|---------------------------------------------------------- |  
|Setuid/Setguid |    s     |     1    | Nếu file được thực thi, người thực thi sẽ là chủ sở hữ|   |  
| Sticky bit    |    t     |     1    | Chỉ chủ sở hữu mới được xóa hoặc thay đổi tên file kể cả  khi Other có toàn quyền vói file đó|  

#### Cách xem phân quyền của một file  
Trong linux,cách đơn giản nhất để xem phân quyền của một file là sử dụng lênh `ls -l`  
Output của câu leenj trên sẽ có dạng như sau: `-rwxr-x-r-x 1 user group`  
 
 * Kí tự `-` đầu tiên là một cờ đặc biết để chỉ loại file,`-` với file thông thường, `d` với thư mục, `c` với thiết bị,`l` với liên kết(liên kết với một file khác).  
 * 3 kí tự rwx đầu tiên là quyền hạn của **Owner**, ở đây Owner sẽ có mọi quyền với file  
 * 3 kí tự r-x ở giữa là quyền hạn của **Group**, ở đây Group sẽ có quyền đọc và quyền dùng lệnh `cd`  
 * 3 kí tự r-x cuối cùng là quyền hạn của **Other**, tương tự như Group ở trên sẽ có quyền đọc và dung lệnh `cd`  
 * Số nguyên đi sau quyền hạn để chỉ số lượng liên kết tới file,ở đây `1` có nghĩa là file này không có liên kết tượng trưng mà chỉ có một liên kết cứng duy nhất trở tới chính nó  
 * Cuối cùng là 2 thông tin nói về chủ sở hữu và nhóm sở hữu, ở đây là người dùng `user` và nhóm `group`  
 
#### Quyền hạn mặc định  

 |    Type    |           Owner       |   Group     |    Other    |  
 |------------|-----------------------|-------------|-------------|  
 |   File     |  rw-(đọc và ghi)cập   | r--(chỉ đọc)  | r--(chỉ đọc) |  
 |  Directory | rwx(đọc,ghi và truy ) | r-x(đọc và truy cập)|r-x(đọc và truy cập) |  
 
 Như vậy, khi tạo file mới, quyền cao nhất luôn luôn thuộc về người tạo ra nó, bao gồm đọc,sửa,xóa...,  
 nhóm người dùng khác chỉ có quyền xem. Với thư mục, mặc dù vẫn dùng chung các kí hiệu r,w,x như file thông thường  
 nhưng quyền hạn có khác một chút cụ thể là:  
    * r(read): quyền xem danh sách file và thư mục con(dùng lênh ls)  
    * w(write): quyền tạo file và thư mục con(dùng lênh touch và mkdir)  
    * x(excute): quyền chuyển vào thư mục (dùng lệnh cd)  
   
#### Quy ước kiểu số:
| Permision | Binary | Number |  
|-----------|--------|--------|  
|     ---   |   000  |    0   |  
|     --x   |   001  |    1   |  
|     -w-   |   010  |    2   |  
|     -wx   |   011  |    3   |  
|     r--   |   100  |    4   |  
|     r-x   |   101  |    5   |  
|     rw-   |   110  |    6   |  
|     rwx   |   111  |    7   |   

Ngoài ra người ta còn sử dụng thêm một bit thứ 4 để biểu diễn suid, sgid và sticky bit  

|   Permision   |   Number  |  
|---------------|-----------|  
|       suid    |   4000    |  
|       sgid    |   2000    |  
|       sticky  |   1000    |  

Mặc định thì khi set permision cho thư mục thì sẽ có tính kế thừa cho các file và các thư mục con  



