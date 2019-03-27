# Phân quyền trong linux  
#### Nhóm phân quyền  
 * Owner: chỉ cấp quyền cho chủ sở hữu của file.  
 * Group: chỉ cấp quyền cho nhóm sở hữu của file.  
 * Other: cấp quyền cho những người dùng và nhóm không thuộc 2 nhóm trên.  
 
### Loại phân quyền  
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

