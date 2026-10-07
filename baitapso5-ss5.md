\# Bài tập 5 TỰ ĐỘNG HÓA BẰNG TERMINAL(powershell)

\# SẢN PHẨM HOÀN CHỈNH

New-Item -Path ".\\Media\\Images", ".\\Study\\Assignments" -ItemType Directory -Force

Move-Item -Path \*.jpg, \*.png, \*.JPG, \*.PNG -Destination ".\\Media\\Images"

Move-Item -Path \*.docx, \*.pdf -Destination ".\\Study\\Assignments"

Remove-Item -Path \*.tmp, \*.cache

New-Item -ItemType Directory kết hợp đối số -Force là tạo chuỗi folder lồng vào nhau

Move-Item là move là di chuyển \*.jpg(tức là lụm hết tất cả các thằng có đuôi là .jpg) vào địa chỉ ta đưa

Remove-Item tức là remove. là xóa vĩnh viễn các file theo đối số đưa vào

