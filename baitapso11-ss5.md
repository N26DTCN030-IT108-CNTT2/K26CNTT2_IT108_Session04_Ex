\# BÀI 11: Thiết kế quy trình tự động hóa sao lưu hóa đơn tại OrderTech (PowerShell)





\## 1. Tự động hóa quy trình (Chuỗi 4 câu lệnh Terminal nối tiếp nhau)



1\. New-Item -Path "Backup" -ItemType Directory -Force

(dùng lệnh New-Item kết hợp đối số -ItemType Directory để tạo thư mục lưu trữ tên là Backup, có thêm -Force cho chắc ăn nếu lỡ thư mục đã tồn tại thì nó không bị lỗi)



2\. Copy-Item -Path "hoadon\_ngay.csv" -Destination "Backup\\hoadon\_ngay.csv"

(dùng lệnh Copy-Item để copy cái file hóa đơn trong ngày hoadon\_ngay.csv vô trỏng thư mục Backup vừa tạo)



3\. Rename-Item -Path "Backup\\hoadon\_ngay.csv" -NewName "hoadon\_2026\_09\_23.csv"

(dùng lệnh Rename-Item để đổi tên file nằm trong thư mục Backup từ hoadon\_ngay.csv thành hoadon\_2026\_09\_23.csv theo đúng ý đề bài)



4\. Remove-Item -Path "hoadon\_ngay.csv"

(dùng lệnh Remove-Item tức là remove để xóa vĩnh viễn file gốc hoadon\_ngay.csv ở thư mục hiện tại, giúp hệ thống sạch sẽ sẵn sàng nhận dữ liệu ngày mới)



\## 2. Xử lý bẫy lỗi quyền (Access is denied)

khi chạy lệnh xóa file mà Terminal réo lên lỗi Access is denied thì do 2 nguyên nhân chính sau:

\- Nguyên nhân 1: cái file hoadon\_ngay.csv đó đang được mở bởi một ứng dụng nào đó trên máy (ví dụ kế toán đang mở Excel coi dữ liệu) nên hệ thống khóa file không cho xóa.

\- Nguyên nhân 2: tài khoản user hiện tại đang bị thiếu quyền quản trị (Administrator) nên không đủ thẩm quyền để can thiệp xóa file trong hệ thống.



cách giải quyết chuẩn chỉnh:

\- Nếu do đang mở ứng dụng thì mình chỉ cần tắt cái phần mềm đang giữ file đó đi là xong.

\- Hoặc nếu thiếu quyền thì mình click chuột phải bật Terminal lên bằng quyền Run as Administrator (nếu xài Windows) hoặc xài thêm sudo (nếu xài Linux/Git Bash) là êm ru.



\## 3. Trình bày Output thông báo

mẫu thông báo hiển thị cho người dùng khi chuỗi lệnh chạy thành công:



\[OK] Backup folder created.



\[OK] Invoice file copied successfully.



\[OK] Backup file renamed successfully.



\[OK] Original invoice file deleted.



\[OK] Daily backup process completed.

