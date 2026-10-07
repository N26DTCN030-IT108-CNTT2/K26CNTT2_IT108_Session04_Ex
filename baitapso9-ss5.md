\# BÀI TẬP SỐ 9 Xử lý sự cố bảo mật file trên Server OrderTech bằng Terminal (PowerShell)



Bước 1: Xác định vị trí

pwd

(lệnh pwd giúp mình kiểm tra chính xác vị trí thư mục hiện tại mình đang đứng trên máy chủ để không bị thao tác nhầm chỗ)



Bước 2: Xác nhận sự cố

ls public

(lệnh ls giúp mình liệt kê toàn bộ file bên trong cái folder public, để mình kiểm tra tận mắt xem có đúng là file db\_password.txt và cái mã độc hacker\_log.bat đang nằm tơ hơ ở trỏng không)



Bước 3: Xử lý bẫy \& Di chuyển an toàn

mkdir secrets

(bước bẫy này cực kỳ quan trọng, mình phải xài lệnh mkdir để tạo cái folder secrets trước. Vì theo nguyên lý, nếu cái folder đích chưa có mặt trên đời, hệ thống sẽ hiểu nhầm secrets là tên file mới, rồi nó tự động đổi tên cái file db\_password.txt thành secrets luôn chứ không thèm chuyển đi đâu hết!)



mv public\\db\_password.txt secrets\\

(sau khi tạo folder xong thì xài lệnh mv để lụm cái file db\_password.txt từ thư mục public quăng vô folder secrets cho an toàn)



Bước 4: Dọn dẹp mã độc

rm public\\hacker\_log.bat

(lệnh rm tức là remove, mình xài lệnh này để tiêu diệt và xóa vĩnh viễn cái file rác hacker\_log.bat bay màu khỏi hệ thống luôn)

