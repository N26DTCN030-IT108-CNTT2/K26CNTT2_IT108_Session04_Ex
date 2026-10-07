# BÀI TẬP SỐ 2

## Phân tích

* B1: lệnh Get-Location giúp mình biết chính xác vị trí đang đứng 

C:\User\<User>\desktop

* B2: liệt kê thư mục bằng lệnh Get-ChildItem. Khi chạy lệnh ở desktop sẽ không thấy file deploy.ps1 vì nó đang nằm ở thư mục khác (download\project)
* B3: gõ deploy.ps1 bị lỗi CommandNotFoundException, vì Power shell sẽ bảo vệ hệ thống nếu có mã độc trùng tên với các lệnh cơ bản khiến user có thể bị nhầm lẫn. cần có tiền tố .\ vì nó là thư mục hiện tại mình đang đứng gọi là current directory. Nếu mình có gõ tiền tố .\ tức là mình đã xác nhận với hệ thống là mình biết file này đang ở thư mục hiện tại. Nếu gõ tiền tố rồi vẫn lỗi thì là do sai thư mục như đã nói

## Sửa lỗi 

### 1. mình sẽ di chuyển từ desk qua download bằng lệnh

Set-Location ..\Downloads\Project



### 2. kiểm tra xác nhân file deploy.ps1 bằng lệnh:

Get-ChildItem hoặc là Test-Path .\deploy.ps1

### 3. chạy thử .\deploy.ps1 thành công

.\deploy.ps1