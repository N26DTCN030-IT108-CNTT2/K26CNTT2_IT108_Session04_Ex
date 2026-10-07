\# BÀI TẬP SỐ 6 Thiết lập cấu trúc dự án IOT bằng termial(powershell)



New-Item -Path "..\\Home\\green-iot", "..\\Home\\bin", "..\\Home\\config", "..\\Home\\data" -ItemType Directory -Force

(Cái này minh dùng lệnh tạo chuỗi folder + đối số -Force để mình tạo chuỗi folder và nếu cái folder đó đã có thì nó bỏ qua bước tạo folder đó và tạo cái tiếp theo. Còn .. là kiểu mình đang ở một folder khác và mình cần lùi ra một bật để di chuyển đến Home theo bài yêu cầu)

2\. New-Item -Path ".\\Home\\config\\pass.env" -ItemType File

(lệnh New-Item -ItemType File là lệnh mình tạo file và .\\ là chỗ mình dang đứng hiện tại và mình muốn tạo file ở địa chỉ này)

3\. Copy-Item -Path "senor\_template.py" -Destination "D:\\Home\\bin\\pump\_controller.py"

(sử dụng lệnh copy file và đổi tên file trên cùng 1 dòng và bắt buộc phải là đường dẫn tuyệt đối đến chính xác vị trí cần paste file vào)

&#x20;## P2 Kiểm thử

vì .env hệ thống sẽ mặc định đây là file bí mật chứa các thông tin quan trọng như API, pass.....

nên sẽ tự động bỏ qua nếu xài lệnh hiển thị list như bình thường

thay vào đó ta sẽ xài lệnh ls -Force để nó hiện tất cả lên.

