\# BÀI TẬP SỐ 8 Khởi tạo cấu trúc module Đồ uống bằng Terminal tại OrderTech (PowerShell)



1\. New-Item -Path "drink\_module" -ItemType Directory

(lệnh New-Item kết hợp đối số -ItemType Directory giúp mình tạo một cái folder mới tên là drink\_module, hoặc nếu lười thì gõ lệnh tắt là mkdir drink\_module cũng được)



2\. cd drink\_module

(lệnh cd là lệnh giúp mình di chuyển chui vào trong cái folder drink\_module vừa mới tạo xong)



3\. New-Item -Path "coffee.txt", "tea.txt" -ItemType File

(lệnh này xài để tạo ra 2 cái file trống cùng một lúc, mình chỉ cần liệt kê tên file cách nhau bằng dấu phẩy là hệ thống tự hiểu và tạo luôn cho lẹ)

