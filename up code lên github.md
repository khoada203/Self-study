## 1. Cách đưa folder lên github

1. Tải git
2. Mở gitbash, cấu hình username và email
(Search google "git config global" để tìm code cấu hình)
- $ git config --global user.name "John Doe"
- $ git config --global user.email johndoe@example.com

3. Mở thư mục muốn đẩy vào git, chuột phải -> Git Bash Here
Gõ các lệnh sau:
- **git init** (Lệnh này tạo ra một thư mục ẩn có tên .git trong thư mục hiện tại. Thư mục này chứa tất cả các thông tin và lịch sử của repository Git.)
- **git remote and origin https://...(link repo)** (Liên kết repository local với repository remote trên GitHub)
- **git remote -v** (Hiển thị tất cả các remote liên kết với repository hiện tại.)
- **git add .** (Mục đích: Thêm tất cả các thay đổi trong thư mục hiện tại vào staging area (khu vực tạm thời) của Git.)
- **git commit -m"note_here"** (Lưu các thay đổi vào repository local với một thông điệp mô tả)
- **git push origin master** (Đẩy các thay đổi từ repository local lên repository remote trên GitHub)

## 2. Thay đổi code và đẩy lên git
**Chỉ cần gõ 3 lệnh sau:**
1. git add.
2. git commit -m"..."
3. git push origin master
