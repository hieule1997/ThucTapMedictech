# Tìm hiểu về git
### 1.Git là gì?
Git là một mô hình quản lí phiên bản phân tán rất tốt thông dụng hiện nay,có thể nó giúp
các lập trình viên quản lí mã nguồn tốt hơn với cơ chế quản lí phiên bản.Ngoài ra nó còn
giúp quy trình làm việc theo nhóm nhanh và đơn giản hơn
Chi tiết hơn.Bạn có thể tìm hiểu [tại đây](https://itviec.com/blog/git-la-gi/)

**2.Các thao tác với git**  
 Cách tạo một remote repository [tại đây](https://www.youtube.com/watch?v=3ivkObtYyHI&list=PLE1qPKuGSJaCGalY_6vhlswzLnTufdWIV&index=11) 
* Cài đặt git trên ubuntu: apt-get install git
* Thiết lập username,email,password cho git:  
  a. *username*: git config --global user.username ******  
  b. *password*: git config --global user.password ******  
  c. *email*: git config --global user.email ******  
* Xóa bỏ username,email,password cho git:  
  a. *username*: git config --global --unset user.username ******  
  b. *password*: git config --global --unset user.password ******
  c. *email*:git config --global --unset user.email ******
* git init: Để khởi tạo Git trong một repository(repo).Nếu không khởi tạo Git,bạn không thể sử
dụng bất kì các câu lệnh Git nào cả.  
* git clone: dùng để sao chép một repository từ trên github về máy local của bạn.  
* git status: kiểm tra trạng thái của code  
* Nhánh trong code(branch): khi sử dụng git bạn có thể tạo ra nhiều nhánh khác nhau  
  a. *git branch*: kiểm tra branch hiện tại  
  b. *git branch <name_branch>*: để tạo ra một branch mới  
  c. *git branch -b <name_branch>*: để chuyển và tạo mới  
* git checkout <name_branch>*: trước khi muốn thay đổi suorce code,điều đầu tiên bạn làm
là checkout một nhá*nh.Để checkout một nhánh bạn dùng câu lênh trên  
* git add . : Sau khi bạn thay đổi source code: thêm mới, sửa ,xóa file ...,Bạn cần phải cập
nhật lên Staging Area.Để cập nhật bạn dùng câu lệnh trên  
* Sau lênh add,bạn sẽ sử dụng câu lệnh Commit để đẩy thông tin thay đổi lên Local Respository:
**git commit -m "Message"**  
* Cập nhật lên server: sau câu lệnh Commit,thông tin mới chỉ được cập nhật lên Local Repository
Nếu muốn cập nhật lên server thì phải sử dụng lệnh push:**git push origin <name_branch>**  
* Ngoài ra, nếu chưa tồn tại remote trên server thì bạn cần phải add mới một remote trước rồi mới push:
**git remote add origin <remote_url>**   sau đó **git push origin <name_branch>**  
* Gộp nhánh:  
Sau một thời gian cập nhật các file và push lên git trên branch mới, bây giờ mình cần ghép (merge) code lại vào nhánh gốc (master). Trước tiên, cần phải checkout ra khỏi branch hiện tại cần gộp để vào branch master, sau đó thì dùng lệnh merge để ghép branch mới vào master:
`git checkout master`
`git merge <new_branch>`
* Xem lại lịch sử commit
**git log**:
Lệnh git log sẽ cho bạn biết về người commit, ngày giờ, message của những lần commit đó.  
* Xem thay đổi trước khi push
 **git diff**: 
Lệnh này giúp bạn biết những gì đã được thay đổi giữa nhánh hiện tại và nhánh trước nó.  
* Gộp commit
**git rebase -i HEAD~**:
Sau dấu ~ là số commit bạn muốn gộp. Sau khi gõ lệnh này một cửa sổ trình soạn thảo hiện ra. Thay đổi ký tự pick của dòng các dòng sau dòng đầu thành s rồi lưu lại/kết thúc. Khi đó, trình soạn thảo để chỉnh sửa giải thích commit thiết lập cho commit sau khi đã tổng hợp sẽ được hiển thị, nên hãy chỉnh sửa lưu lại/kết thúc.  
* Pull từ remote repository
**git pull origin master**:
Lệnh trên sẽ gộp những thay đổi mới kéo về từ máy chủ từ xa với nhánh hiện tại trên máy local.