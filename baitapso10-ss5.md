\# BÀI TẬP SỐ 10 Phân tích và lựa chọn phương thức quản lý thư mục cho hệ thống OrderTech



\## P1 Phân tích \& Đề xuất

cách 1: dùng GUI (giao diện đồ họa). tức là mình sẽ thao tác thủ công bằng chuột, click chuột phải -> chọn New Folder rồi gõ tên... cứ thế lặp đi lặp lại 50 lần.

cách 2: dùng CLI (giao diện dòng lệnh). mình sẽ xài terminal (PowerShell) để viết một dòng lệnh duy nhất, tạo một phát ra luôn 50 cái thư mục.



\## P2 So sánh \& Lựa chọn

so sánh giữa GUI và CLI:



| Tiêu chí | GUI | CLI |

| :---: | :---: | :---: |

| Tốc độ thực hiện | Chậm rì rề, click mỏi tay và dễ tốn thời gian. | Siêu tốc độ, gõ 1 dòng lệnh Enter là xong ngay 50 cái. |

| Khả năng lặp lại/Tự động hóa | Gần như bằng không, mốt có thêm 100 chi nhánh thì lại phải click lại từ đầu. | Tính tự động hóa cực kỳ cao, mình lưu script lại mốt chạy 1 giây là xong. |

| Mức độ dễ học cho người mới | Rất dễ, ai cũng quen xài chuột nên nhìn là làm được liền. | Hơi khó lúc đầu vì phải học thuộc câu lệnh và gõ đúng cú pháp. |



chốt giải pháp: mình chắc chắn sẽ chọn cách 2 (CLI). 

(lý do: dự án chỉ cho 1 giờ và yêu cầu tính chính xác 100%. xài CLI giúp mình tạo hàng loạt thư mục chuẩn không cần chỉnh, tránh được rủi ro con người như gõ sai chính tả tên folder hoặc tạo thiếu lúc làm bằng tay. nó cứu sống cả dự án chỗ đó.)



\## P3 Thiết kế thao tác

ví dụ lệnh PowerShell để tạo 3 folder Ban, Kho, Menu:



New-Item -Path "Ban", "Kho", "Menu" -ItemType Directory

(lệnh New-Item kết hợp với đối số -ItemType Directory giúp mình tạo nhiều folder cùng lúc. mình chỉ cần liệt kê tên thư mục trong ngoặc kép rồi cách nhau bằng dấu phẩy là hệ thống tự hiểu và tạo luôn cho lẹ. ngoài ra lười thì có thể gõ tắt là mkdir Ban, Kho, Menu cũng được)

